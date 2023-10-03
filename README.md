# Stable-Diffusion-Prompt-RAG
This is a demo of improving Stable Diffusion prompts with Retrieval-Augmented Generation (RAG) using Amazon Bedrock models:
- Text Generation: [Claude V2](https://aws.amazon.com/bedrock/claude/) "anthropic.claude-v2"
- Text Embedding: [Titan embedding](https://aws.amazon.com/bedrock/titan/) "amazon.titan-embed-text-v1"
- Image Generation: [Stable Diffusion XL](https://aws.amazon.com/bedrock/stable-diffusion/) "stability.stable-diffusion-xl-v0"
- Vector Database: FAISS
- Prompt Database: a subset from [DiffusionDB](https://huggingface.co/datasets/poloclub/diffusiondb) on Hugging Face

### 1. Download this git repo and setup the RAG Application in Sagemaker Studio or EC2 instance.

### 2. Configure environment variables using the command blueprints below:
```
export BWB_ENDPOINT_URL=https://IF_YOU_WERE_PROVIDED_A_SPECIAL_ENDPOINT_URL_IT_GOES_HERE.com
export BWB_PROFILE_NAME=IF_YOU_NEED_TO_USE_AN_AWS_CLI_PROFILE_IT_GOES_HERE
export BWB_REGION_NAME=REGION_NAME_GOES_HERE_IF_YOU_NEED_TO_OVERRIDE_THE_DEFAULT_REGION
```
Check [Amazon Bedrock Doc](https://docs.aws.amazon.com/bedrock/latest/userguide/endpointsTable.html) for details
You can run the following commands to confirm that your environment variables are set properly:
```
echo $BWB_ENDPOINT_URL
echo $BWB_PROFILE_NAME
echo $BWB_REGION_NAME
```
### 3. Install the required python libraries by running the command: 
```
pip install -r requirements.txt
```

### 4. Prepare the dataset of 1K prompt examples from DiffusionDB by running the command:
```
python imgrag_prep.py
```
Note: This step will take about 1-2 mins. 

### 5. Run the application using the command by running the command:
```
streamlit run app.py
```
This will start a web browser and the url will be printed to the command line. 


