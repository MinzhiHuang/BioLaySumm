1. Overall, this project is well organized and well executed. 
2. The wandb page is very well organized. Please sync all your subsequent model results to the same page and use the exact same test set. Later you will use it to compare the performance of different models.
3. The reference format is incorrect. Please check the original ACL template, which should contain a section on how to cite papers. It is not OK to only attach a link to the original pdf. 
4. Some tables and formulas are not over the margin. Please check the Overleaf instructions to learn about how to typeset tables and formulas. 
5. Given that the texts in this tasks are very long, you can consider methods for downsampling the texts. The importance of different sections for summarization is like: abstract > introduction = conclusion >> any other sections. You can also try some methods for predicting the relevance of individual sentences to summarization. You can try retrieval models like sentence transformers, or E5 to generate the relevance.
6. For language models, you don't always need to train or finetune a model. Finding some clever methods to prompt an LLM like Mistral-7b can sometimes give you reasonable results.    
7. For error analysis, it is not enough to simply place model predictions in your Github. Please write a few sentences about the error analysis in your progress report after inspecting model outputs. 