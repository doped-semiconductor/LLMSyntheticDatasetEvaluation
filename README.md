# LLM based Synthetic Dataset Generation and Automated Evaluation

Predictive intelligence is revolutionizing workflows across industries by enabling data-driven decision-making and process optimization. Central to its success is the availability of high-quality data, yet access to such data often presents a significant challenge. Issues related to data privacy, limited accessibility, and scarcity hinder the development of robust predictive systems. Synthetic data generation has emerged as a powerful solution to address these limitations, offering a means to create diverse, high-quality datasets while preserving privacy and overcoming data availability constraints. The rapid development of large language models (LLMs) has further expanded the possibilities for synthetic data generation. These models, equipped with advanced natural language understanding and generation capabilities, hold great promise for creating synthetic datasets tailored to specific applications. However, the growing diversity of LLMs also presents a critical question: which model is best suited for a particular data generation task? Identifying the ideal combination of synthetic data generation techniques and LLMs for a given problem statement is essential to maximize efficiency and effectiveness. This study proposes a systematic methodology to objectively compare and evaluate the suitability of different LLMs and data generation approaches for specific tasks. 


## Zero/One Shot Data Generation Notebooks

Zero-shot prompting involves instructing the LLM to perform a task without providing any examples. The prompt includes only a description of the task and what the desired output should look like.

The following notebooks are used along with the prompt to generate zero shot prompted data for the three LLMs.

>notebooks\02_1_gpt2_zs_gen.ipynb

>notebooks\02_2_flan_zs_gen.ipynb

>notebooks\02_3_llama_zs_gen.ipynb


### Prompts
These may be modified.
```
prompts = {
    'spam': 'Text message with advertisement or offer',
    'non_spam':'Text message from a friend or family says',
    'real_news':'Recently published political news title',
    'fake_news':'Fake political news title',
    'happy_tweet':'Tweet as a happy person',
    'sad_tweet': 'Tweet as a sad person'
}
```

## Few Shot Data Generation Notebooks

Few-shot prompting involves providing a small number of examples along with the task description. This helps the model better understand the desired format and characteristics of the output.

>notebooks\02_4_fsl_cluster.ipynb

>notebooks\02_4_fsl_prompt_gen.ipynb

## Paraphrasing Shot Data Generation Notebooks

Paraphrasing involves using LLMs to rephrase existing data into new forms while retaining the original meaning. This technique is useful for augmenting datasets by increasing diversity and reducing redundancy.

The following notebooks are used to generate paraphrased data.

>notebooks\02_5_flan_pp_gen.ipynb

>notebooks\02_5_gpt2_pp_gen.ipynb

>notebooks\02_5_llama_pp_gen copy.ipynb

## Training and Evaluation Notebooks

BERT based classifier trained using the generated data.

With the following constant parameters
```
ZERO_SHOT = "zs"
FEW_SHOT = "fs"
PARAPHRASE = "pp"

GPT2 = "gpt2"
FLAN = "flan"
LLAMA = "llama"
```

The user may modify these
```
DATASET_TYPE = ZERO_SHOT
LLM = LLAMA
```

The training will be facilitated with the following notebook.

>notebooks\03_general_trainer.ipynb

The overall evaluation may be conducted with the following notebook.

>notebooks\05_eval_test.ipynb
