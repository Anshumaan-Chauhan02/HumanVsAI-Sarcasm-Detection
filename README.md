<h2>
<p align='center'>
 HumanVsAI-Sarcasm-Detection
</p>
</h2>

**Dataset Collection** \\
I collected a sample of 120 non-sarcastic sentences from https://github.com/iabufarha/iSarcasmEval/blob/main/train/train.En.csv. Out of 120 sentences, 60 sentences were sampled randomly, and were converted into a sarcastic one using ChatGPT. Prompt was to rephrase the sentence into a sarcastic one while keeping the length similar to the input sentence. Fo the remaining 60 samples, the dataset had the corresponding sarcastic conversions done by a human. 

**Task Description** \\
The binary text classification task was to differentiate whether the sarcastic sentence made by a Human or an AI. The reason behind choosing this task was - we usually are not capable of easily figuring out whether the text is saracstic or not. Now considering that it is sarcastic, it is even harder to differentiate between a sarcastic sentence by a Human and an AI. Though there are some characteristics that can be used to figure out whether a sentence is made by an AI, but LLMs such as ChatGPT usually do not reflect such behavior in short sentences. Maybe this is evident in a paragraph or a short story.
