# Investigating the Shortcomings of LLMs in Step-by-Step Legal Reasoning

Our paper: [https://arxiv.org/abs/2502.05675](url)

### Instructions to obtain the dataset:
For obtaining permission to use the 'Civ. Pro.' dataset evaluated in our research paper, please refer and follow the steps as outlined in the following github link:
[https://github.com/trusthlt/legal-argument-reasoning-task](https://github.com/trusthlt/legal-argument-reasoning-task)

### Instructions to run the LLM inferences:
Please refer to the prompt-format in 'Legal-Reasoning-zero-shot-prompt-for-LLM-inference.py' for zero-shot CoT LLM inference

### Instructions to run auto-evaluator pipeline:
The project was tested using python 3.10.

Please use the following commands to setup the environment:
```
python -m venv legal_reasoning

# Activate the virtual environment (macOS/Linux)
source venv/bin/activate

# Activate the virtual environment (Windows): .\venv\Scripts\activate

# Install dependencies from requirements.txt
pip install -r requirements.txt
```

Run the notebooks 'Legal-Reasoning-Auto-Evaluator-Pipeline.ipynb' and 'Legal_Reasoning_Metrics_Calculation.ipynb' sequentially to run first run the auto-evaluator pipeline and then compute the 'Soundness', 'Correctness' and 'Accuracy' metrics as discussed in the paper.

### Instructions to run mitigation techniques:
Download Lllama models from [huggingface](https://huggingface.co/meta-llama).
Add your data path and the output path.

Run the baseline code as follows.

```python baseline.py```

To run other prompting techniques with error feedbacks, specify the feedback type from ```long```, ```short``` or  ```generic```.
As an example, you can run plan and solve technique with descriptive error feedbacks as follows.

```python plan-and-solve-w-errors.py --feedback long```

#### Additional Note:
There are various places in 'Legal-Reasoning-Auto-Evaluator-Pipeline' and 'Legal_Reasoning_Metrics_Calculation' where the paths of input and output files need to be provided for loading and saving of results. OpenAI API key is required to be provided in the appropriate place for the auto-evaluator pipeline to work.

### Citation:
Our work can be cited through:
```
@inproceedings{mishra-etal-2025-investigating,
    title = "Investigating the Shortcomings of {LLM}s in Step-by-Step Legal Reasoning",
    author = "Mishra, Venkatesh  and
      Pathiraja, Bimsara  and
      Parmar, Mihir  and
      Chidananda, Sat  and
      Srinivasa, Jayanth  and
      Liu, Gaowen  and
      Payani, Ali  and
      Baral, Chitta",
    editor = "Chiruzzo, Luis  and
      Ritter, Alan  and
      Wang, Lu",
    booktitle = "Findings of the Association for Computational Linguistics: NAACL 2025",
    month = apr,
    year = "2025",
    address = "Albuquerque, New Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.findings-naacl.435/",
    doi = "10.18653/v1/2025.findings-naacl.435",
    pages = "7810--7841",
    ISBN = "979-8-89176-195-7",
}
```
