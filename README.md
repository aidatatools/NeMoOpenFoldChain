# NeMoOpenFoldChain

NeMo OpenFold LangChain for NVIDIA GenAI Contest

<https://www.nvidia.com/en-us/ai-data-science/generative-ai/developer-contest-with-langchain/terms-and-conditions/>

## Desired and Required Libraries

- nemo-toolkit 1.23.0
- langchain 0.2.5

## Step 1: Set Up Your Environment

1. **Hardware Requirements**: Ensure you have access to NVIDIA GPUs, ideally A100, to run the models efficiently. In my case I rent A100 GPU from Digital Ocean Paperspace. Please see the screenshot. Disk Size: 1TB

   ![create_a_new_machine](img/create_a_new_machine.png "create_a_new_machine")


1. **venv**:

   Ensure you have Python 3.10 or later installed.

   ```bash
   cd ~
   python3.11 -m venv venv
   source venv/bin/activate
   ```

1. First resolve **YouTokenToMe Cython** issue:

   ```bash
   cd ~
   git clone git@github.com:aidatatools/NeMoOpenFoldChain.git
   cd NeMoOpenFoldChain
   cd YouTokenToMe
   pip install -e .
   ```

1. **NeMo Toolkit**:

   ```bash
   cd ~
   cd NeMoOpenFoldChain
   pip install "nemo_toolkit[all]"
   ```

1. Install **LangChain** Dependencies:

   ```bash
   cd ~
   cd NeMoOpenFoldChain
   pip install langchain

   ```

1. Install **OpenFold**

   ```bash
   #Install conda and then mamba
   cd ~
   wget https://repo.anaconda.com/miniconda/Miniconda3-py311_24.4.0-0-Linux-x86_64.sh
   chmod +x Miniconda3-*-Linux-x86_64.sh
   ./Miniconda3-*-Linux-x86_64.sh
   ```

   If you'd prefer that conda's base environment not be activated on startup,
   run the following command when conda is activated:

   conda config --set auto_activate_base false

   ```bash
   # Install Mamba via Conda
   cd ~
   source ~/.bashrc
   conda install -c conda-forge mamba
   #~/miniconda3/bin/conda install mamba -n base -c conda-forge
   ```

   <https://openfold.readthedocs.io/en/latest/Installation.html>

   ```bash
   #In my environment, I have CUDA 12.1, so pay attention to the branch name
   cd ~
   git clone -b pl_upgrades https://github.com/aqlaboratory/openfold.git
   cd openfold
   mamba env create -n openfold_env -f environment.yml
   #Activate the environment, e.g
   conda activate openfold_env
   scripts/install_third_party_dependencies.sh
   conda deactivate
   conda activate openfold_env
   export LD_LIBRARY_PATH=$CONDA_PREFIX/lib:$LD_LIBRARY_PATH
   ./scripts/download_openfold_params.sh ~/openfold/resources
   #Checking your build with unit tests:
   scripts/run_unit_tests.sh
   ```
