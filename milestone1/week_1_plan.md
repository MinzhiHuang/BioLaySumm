1. **Planning to Build a Baseline Model:**
   - **Objective:** Firstly, to define the specific problem that we're addressing—here, it's about creating lay summaries (more information but using less technical terminology) from biomedical research articles.
   - **Dataset Assembly:** We’ll use the publicly available biomedical datasets (like PLOS and eLife) that include research articles and their lay summaries. We will ensure that we have a clean, split dataset for training, validation, and testing.
   - **Model Selection:** For a baseline we can start with a simple model/approach to establish a performance baseline. We could use TF-IDF with Logistic Regression to classify each sentence or paragraph as relevant (should be included in the summary) or not. 

2. **Pretrained Model for Use:**
   - We'd consider using a pretrained model like BERT or its variants (e.g. BioBERT or BioMedLM, specifically pre-trained in biomedical literature) for feature extraction. For the actual task of summarization, T5 (Text-to-Text Transfer Transformer) or GPT (Generative Pretrained Transformer) could be excellent starting points. These models have been trained on vast amounts of text and can be fine-tuned for specific tasks like summarization.

3. **Hardware for Model Development:**
   - **CPUs vs. GPUs:** For training deep learning models, especially those involving large pretrained models like BERT or T5, GPUs are highly recommended due to their faster matrix computation capabilities. 
   - **Memory Requirements:** Deep learning models, particularly when we’re working with large datasets or fine-tuning large pretrained models, can be memory-intensive. We plan to use multiple Kaggle free tier GPUs that come with 16 GB VRAM, if required we can also move to Colab Pro for higher compute.

4. **Reasons to Use This Model:**
   - **Pretrained Models:** Utilizing models like BERT, BioBERT, T5, or GPT for summarization tasks comes with several advantages. They have been trained on extensive corpora, capturing a wide range of language nuances and structures. This pre-training helps in understanding complex biomedical text.
   - **Adaptability:** These models can be fine-tuned with varying amounts of task-specific data, making them highly adaptable to specialized tasks such as generating lay summaries from biomedical research articles.
   - **Performance:** Pretrained models have demonstrated state-of-the-art performance across a variety of NLP tasks, including summarization. Their ability to generate coherent, relevant, and informative text makes them particularly suitable for creating summaries intended for non-expert audiences.
