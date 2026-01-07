# ML-Code-Analyzer
The goal of this project is to use prompt engineering to create a ml code analyser using existing models. I an using hugging face free models as well as state of the art models to do the task. For a code i am using
an example code, in that I will generate multiple chains of thoughts and calcultate self consistency amongst them. Naturally the chain with the highest consistency is the best. The goal is to take a ml code and help in improving it.

## Models used
From hugging face, I tried the 3 models on kaggle which are standard small models:

- TinyLlama-1.1B-Chat-v1.0
- phi-2
- Qwen2.5-1.5B-Instruct

and also used perplexity pro(Sonar model)

## Observations
At first I ran the example code for 2 chains. Only phi-2 was able to show that it can generate properly with prompts. Then I used 20 chains for that model only to see the working and get best response. Basically, I wanted to get a good response for my prompt (which helps in the ml code analysis) by first choosing a model, 2ndly to pick the best answer from the model by generating different answer(chains) by using various temparatures to modify creativity. Finally, I also compared it to whether the result was good enough compared to a standard AI tool available to us(example: perplexity)

    

## Phi-2 results

<img width="847" height="647" alt="Image" src="https://github.com/user-attachments/assets/0e141abd-6a34-43c6-a8b6-cf7a9ad49bf7" />

<img width="960" height="362" alt="Image" src="https://github.com/user-attachments/assets/c3047235-cf6b-4710-b5f4-08d6f0f2e825" />

## Perplexity Output

Execution Summary
Generated chains at temperatures 0.60–0.87, with top agreements around 0.945–0.909. Chain 3 ranked highest due to maximal lexical overlap across peers.
​

Best Chain Reasoning
Step 1: Understanding the Goal
This code aims to predict 'Disease' from a medical dataset 'indianmedico.csv' using Random Forest classification.
​

Step 2: Data Analysis
Loads CSV with pandas, assumes columns like Age, Sex, Name, Disease. No shape/info print.
​

Step 3: Preprocessing Quality
Fills NaN Age with global mean - potential overfitting. Dummifies Sex only. Drops Name from X.
​

Step 4: Model Selection
RandomForestClassifier suitable for tabular medical data, handles mixed types well.
​

Step 5: Training & Evaluation
80/20 split, fit on train, predict test, print accuracy. No CV or other metrics.
​

Step 6: Identify Issues
Data leakage in imputation; Name drop problematic if string; no scaling/balance handling.
​

Step 7: Recommendations
Use Pipeline for split-aware preprocess, add CV, class weights, EDA.

## Conculsion

Therefore using prompt engineering techniques(such as chains of thoughts with self consistency) we can choose and use pre-existing models for very specific task, in my case a ML Code Analyzer.

## Blockers

Most of the free hugging face models are really not good for CoTs especially for my task as they either kept repeating the prompt or missing the goal of analyzing the codde. I also tried using api calls instead from hugging face but I kept getting authorization issues, so I opted for just downloading small models.


