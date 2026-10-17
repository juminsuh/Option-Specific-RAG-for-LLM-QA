# Team5_NLP_Upstage
[25-2 NLP] Term Project. Enhancing a QA performance of LLM (Solar Pro 2) using RAG and Prompt engineering.

### 📌 Key Features
1. We used a LLM router to utilize different prompts depending on the question type (EWHA or MMLU).
2. We parsed a table into a raw text, which enables LLM to understand better.
3. We implement RAG for each option, motivated by running RAG once for the 'Question + All Options' often fails to retrieve sufficient context for every specific options.
4. We wrote prompts by empirically adding execution protocols based on the mistakes the model made, such as verification, the format of output, and etc. 
5. We leveraged ensemble in order to ensure a more stable and robust final answer through majority voting.

### System Architecture


### ✨ Results

- EWHA: 100% (25/25)
- MMLU: 76% (19/25)
- Total: 88% (44/50)


### 🛠️ Setting

1. Clone this repository to your local.
   ```
   git clone https://github.com/juminsuh/Team5_NLP_Upstage.git
   ```
2. Please download ```faiss_vectorstore``` folder from [google drive](https://drive.google.com/drive/u/0/folders/1XI0D3OtXREUscMaqnuW2oKZk7bM7KV6U). (😂 It might take a few minutes due to it's large size (i.e., 1.1GB))
3. Unzip ```faiss_vectorstore```.
4. Make sure to set the ```faiss_vectorstore``` directory such as ➡️ ```./Team5_NLP_Upstage/faiss_vectorstore```
5. Make `.env` file and write ```UPSTAGE_API_KEY="your_upstage_api_key"``` to ```.env``` file. (The directory of your `.env` file is ```./Team5_NLP_Upstage/.env```)

### 🔗 Requirements

1. Create your virual enviroment and activate it
```
conda create -n team5 python=3.10 -y # create
conda activate team5 # activate
```
2. Install
```
pip install -r requirements.txt
```

**🥳 You are ready to run the code!**


### 🔥 Implement run.py
---
```
python run.py --data_path ./datasets/testset.csv
```
➡️ If you want to evaluate other testset, then just change the value of `--data_path`.
```
python run.py --data_path <your_testsets_directory>
```
✅ You can check total score by running the code below (You should modify the directory of score.py appropriately before you run the code):
```
python score.py
```

### 📚 Source

We utilized textbook and QA datasets from hugging face. 
* [law_001](https://huggingface.co/datasets/ymoslem/Law-StackExchange) [law_002](https://huggingface.co/datasets/reglab/barexam_qa)
* [philosophy_001](https://huggingface.co/datasets/burgerbee/philosophy_textbook) [philosophy_002](https://huggingface.co/datasets/burgerbee/religion_textbook) [philosophy_003](https://huggingface.co/datasets/sayhan/strix-philosophy-qa)
* [business_001](https://huggingface.co/datasets/theoldmandthesea/17k_business_book) [business_002](https://huggingface.co/datasets/warrencain/Business_Knowledge_Dataset_Llama_3.1_Short_Token_Pairs)
* [history_001](https://huggingface.co/datasets/nielsprovos/world-history-1500-qa) [history_002](https://huggingface.co/datasets/burgerbee/history_textbook)
* [psychology_001](https://huggingface.co/datasets/BoltMonkey/psychology-question-answer) [psychology_002](https://huggingface.co/datasets/burgerbee/psychology_textbook/viewer/default/train?row=99&views%5B%5D=train)
