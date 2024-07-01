### Problem: 
LLMs are constantly changing, and users lack the ability to reliably categorize the responses from LLMs as accurate, truthful, biased, or incorrect. 


## Part 1: Identifying Unlabeled Bias through Vector Distances from Median
[Code here.](poc_text_vector_comparison_analysis.ipynb)

### Hypothesis: 
Through the utilization of text vectoring analysis, we can detect bias within LLMs by identifying outliers relative to the median or mean vectors.

### Methodology: 
* Interrogate 3 OpenAI models with identical static prompts. 
* Tokenize the responses into numeric vectors using BERT.
* Compare euclidian distances of the vectors to identify mean, median, standard deviation, average distances, etc.
* Use Z-Scores to identify outliers from those vectors, while also providing the capability to stack-rank the vectors based on those distances.
* Presume some bias (un-labeled at this point) exists for outlier vectors.

### Success Criteria: 
* Accuracy of Bias Detection.
  - By manually injecting a biased answer and comparing it to an unaltered set, we should be able to identify bias (threshold TBD). 
* Robustness to variability in Prompts.
  - By changing the prompt slightly, we should see similar vector scores. Comparing those vectors to prior vectors should yield short average distances.
* Repeatability and Consistency where Expected. 
  - By re-running the same prompts over time, we should see similar if not identical vector scores with constant responses.

### Future Work
* Multiple pre-created "users" - identify cognitative biases
* Build and Analyze Confusion Matrix to better study and understand performance. 
