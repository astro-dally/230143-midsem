# AML Midsem — Paper Reproduction

**Student:** Dally R  
**Roll Number:** 230143  
**Course:** Advanced Machine Learning  
**Institution:** Rishihood University — Newton School of Technology

## Paper

**[Learning Kernels with Radiuses of Minimum Enclosing Balls](https://proceedings.neurips.cc/paper/2010/file/05049e90fa4f5039a8cadc6acbb4b2cc-Paper.pdf)**  
Kun Gai, Guangyun Chen and Changshui Zhang — NeurIPS 2010

## Structure

```
230143-midsem/
├── final paper.pdf
├── partA/
│   └── llm_usage_partA.json
└── partB/
    ├── report.tex
    ├── requirements.txt
    ├── task_1_*.ipynb       # Paper understanding
    ├── task_2_*.ipynb       # Reproduction experiments
    ├── task_3_*.ipynb       # Ablation & failure analysis
    ├── llm_task_*.json      # LLM usage disclosures
    ├── data/
    └── results/
```

## Running

```bash
pip install -r partB/requirements.txt
cd partB
jupyter notebook
```

## Dataset

Synthetic — generated using `sklearn.datasets.make_classification`. No external download required.
