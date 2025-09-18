# BioLaySumm: Biomedical Lay Summarization

**Team Bossy Beaver** - COLX 531 Project  
*Participated in BioLaySumm 2023 Shared Task @ ACL 2023 BioNLP Workshop*

## 👥 Team Members

- **Minzhi Huang**
- **Minh Nguyen**
- **Hayden Chiu**
- **Tushar Choudhary**
- **Hui Yin Lam**

## 🎯 Project Overview

This project focuses on **biomedical lay summarization** - automatically generating accessible, non-technical summaries from complex biomedical research articles. The goal is to make scientific research understandable to non-expert audiences by transforming technical content into readable summaries with simplified terminology and background information.

### Task Description

- **Input**: Biomedical research articles (abstracts + main text) from PLOS and eLife journals
- **Output**: Lay summaries that are accessible to general audiences
- **Challenge**: Balance accuracy, readability, and factual consistency while maintaining scientific integrity

## 📊 Performance Results

### Final Performance Metrics (Milestone 6)

Our best performing model achieved the following results on the full development set:

| Metric | Score | Improvement |
|--------|-------|-------------|
| **ROUGE-1** | 0.410 | ↑6.5% from baseline |
| **ROUGE-2** | 0.127 | ↑10.3% from baseline |
| **ROUGE-L** | 0.380 | ↑8.6% from baseline |
| **BERTScore** | 0.851 | High semantic similarity |
| **FKGL** | 13.23 | ↓11.3% (improved readability) |
| **DCRS** | 10.38 | ↓11.8% (improved readability) |
| **CLI** | 14.97 | ↓11.8% (improved readability) |
| **LENS** | 65.57 | Factuality score |
| **AlignScore** | 0.809 | Factuality alignment |
| **SummaC** | 0.673 | Factuality consistency |

### Baseline Comparison

| Metric | Baseline | Final | Improvement |
|--------|----------|-------|-------------|
| ROUGE-1 | 0.385 | 0.410 | +6.5% |
| ROUGE-2 | 0.115 | 0.127 | +10.3% |
| ROUGE-L | 0.350 | 0.380 | +8.6% |
| FKGL | 14.92 | 13.23 | -11.3% |
| DCRS | 11.77 | 10.38 | -11.8% |
| CLI | 16.98 | 14.97 | -11.8% |

## 🚀 Technical Approach

### Model Architecture

We implemented a **multi-model approach** combining several state-of-the-art language models:

1. **BioMistral-7B** - Biomedical domain-specific model
2. **GPT-3.5 Turbo** - OpenAI's general-purpose model  
3. **Mixtral-8x7B** - Mixture of experts architecture

### Key Innovations

- **Few-shot Learning**: Implemented 5-shot prompting strategies for improved performance
- **Model Optimization**: Used 4-bit quantization for efficient inference
- **API Integration**: Leveraged Groq API for ultra-fast cloud inference
- **Local Deployment**: Used vLLM framework for efficient local model serving

### Technical Stack

- **Python** - Primary development language
- **Transformers** - Hugging Face model library
- **vLLM** - High-performance inference framework
- **Groq API** - Ultra-fast cloud inference
- **OpenAI API** - GPT-3.5 integration
- **Wandb** - Experiment tracking and logging

## 📁 Project Structure

```
BioLaySumm-main/
├── milestone1/          # Project planning and data exploration
├── milestone2/          # Data extraction and baseline models
├── milestone3/          # Transformer baseline implementation
├── milestone4/          # Large language model exploration
├── milestone5/          # Few-shot learning optimization
├── milestone6/          # Final optimization and deployment
├── data/               # Datasets and evaluation results
└── README.md           # This file
```

## 🔬 Evaluation Metrics

The project uses comprehensive evaluation across three dimensions:

### Relevance Metrics

- **ROUGE-1/2/L**: Measures n-gram overlap with reference summaries
- **BERTScore**: Semantic similarity using contextual embeddings

### Readability Metrics  

- **FKGL**: Flesch-Kincaid Grade Level (lower = more readable)
- **DCRS**: Dale-Chall Readability Score (lower = more readable)
- **CLI**: Coleman-Liau Index (lower = more readable)

### Factuality Metrics

- **LENS**: Language Evaluation for Non-factual Summaries
- **AlignScore**: Factual alignment between source and summary
- **SummaC**: Factual consistency checking

## 🏆 Key Achievements

1. **Performance Improvement**: Achieved 6.5% improvement in ROUGE-1 score
2. **Readability Enhancement**: Reduced FKGL by 11.3%, making summaries more accessible
3. **Multi-model Integration**: Successfully combined multiple LLM architectures
4. **Efficient Inference**: Implemented both cloud and local deployment strategies
5. **Comprehensive Evaluation**: Used 10 different metrics across relevance, readability, and factuality

## 🛠️ Setup and Usage

### Prerequisites

```bash
pip install -r requirements.txt
```

### Running Evaluation

```bash
python evaluate.py /path/to/predicted/summaries /path/to/validation/data
```

### Model Inference

```python
# Example usage with vLLM
from vllm import LLM, SamplingParams

llm = LLM(model="BioMistral-7B")
sampling_params = SamplingParams(temperature=0.7, top_p=0.9)
outputs = llm.generate(prompts, sampling_params)
```

## 📚 References

- [BioLaySumm 2023 Shared Task](https://biolaysumm.org/2023/)
- [ACL 2023 BioNLP Workshop](https://acl2023.org/)
- [PLOS Dataset](https://journals.plos.org/)
- [eLife Dataset](https://elifesciences.org/)
