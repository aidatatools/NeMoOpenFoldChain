# NeMoOpenFoldLangChain

NeMo OpenFold LangChain for NVIDIA GenAI Contest

<https://www.nvidia.com/en-us/ai-data-science/generative-ai/developer-contest-with-langchain/terms-and-conditions/>

## Step 1: Set Up Your Environment

1. **Hardware Requirements**: Ensure you have access to NVIDIA GPUs, ideally A100, to run the models efficiently. In my case I rent A100 GPU from Digital Ocean Paperspace. Please see the screenshot. Disk Size: 1TB

   ![create_a_new_machine](img/create_a_new_machine.png "create_a_new_machine")


1. **Check if you can run Docker**:

   ```bash
   #Add Your User to the Docker Group
   sudo usermod -aG docker $USER
   ＃Log Out and Log Back In
   groups $USER
   ＃You should see docker listed in the output.
   ```

1. **Pull the NeMo Framework Container**:

   ```bash
   docker pull nvcr.io/nvidia/nemo:23.10
   ```

1. **Run the Container**:

   ```bash
   docker run --gpus all -it --shm-size=1g --ulimit memlock=-1 --ulimit stack=67108864 nvcr.io/nvidia/nemo:23.10
   ```

1. **Install Required Python Packages Inside the Container**:

   ```bash

   #LangChain
   pip install langchain

   #LangChain
   pip install langchain

   #LangChain
   pip install langchain

   #LangChain
   pip install langchain

   #LangChain
   pip install langchain

   #LangChain
   pip install langchain


   ```
