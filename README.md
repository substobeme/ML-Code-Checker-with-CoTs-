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

## Prompt Used
<|system|>
    You are an expert ML engineer. Use step-by-step reasoning to analyze code.</s>
    <|user|>
    Analyze this ML code using chain of thought. Think through each step explicitly.
   
    
    Let's think step by step:
    
    Step 1: Understanding the Goal
    What is this code trying to accomplish?
    
    Step 2: Data Analysis  
    Examine the data handling and loading.
    
    Step 3: Preprocessing Quality
    Evaluate the preprocessing steps.
    
    Step 4: Model Selection
    Is the model choice appropriate?
    
    Step 5: Training & Evaluation
    How is training and evaluation done?
    
    Step 6: Identify Issues
    What problems or risks exist?
    
    Step 7: Recommendations
    What improvements should be made?
    
    Work through each step carefully, explaining your reasoning.</s>
    <|assistant|>
    Let me think through this step by step:
    
    Step 1: Understanding the Goal
    

## Phi-2 results

<img width="847" height="647" alt="Image" src="https://github.com/user-attachments/assets/0e141abd-6a34-43c6-a8b6-cf7a9ad49bf7" />

<img width="960" height="362" alt="Image" src="https://github.com/user-attachments/assets/c3047235-cf6b-4710-b5f4-08d6f0f2e825" />
