<h2>
<p align='center'>
 HumanVsAI-Sarcasm-Detection
</p>
</h2>

### Dataset Collection 
I collected a sample of 120 non-sarcastic sentences from https://github.com/iabufarha/iSarcasmEval/blob/main/train/train.En.csv. Out of 120 sentences, 60 sentences were sampled randomly, and were converted into a sarcastic one using ChatGPT. Prompt was to rephrase the sentence into a sarcastic one while keeping the length similar to the input sentence. Fo the remaining 60 samples, the dataset had the corresponding sarcastic conversions done by a human. 

### Task Description
The binary text classification task was to differentiate whether the sarcastic sentence made by a Human or an AI. The reason behind choosing this task was - we usually are not capable of easily figuring out whether the text is saracstic or not. Now considering that it is sarcastic, it is even harder to differentiate between a sarcastic sentence by a Human and an AI. Though there are some characteristics that can be used to figure out whether a sentence is made by an AI, but LLMs such as ChatGPT usually do not reflect such behavior in short sentences. Maybe this is evident in a paragraph or a short story.

### Future Work 
   1) In the future I would have collected datasets that have each entry with multiple sentences and long sequences, in order to fully utilize the errors that are made by AI models in such cases - such as sudden change of tone/sentiment and unusual facts (or structures) used that are not relevant. This would help the Machine Learning model to learn those characteristics and make more accurate predictions. Create a proper AI vs Human dataset, where ChatGPT, GPT3, and other AI models will be used to generate the AI samples and will be labeled correctly (not use human annotators). This would lead to have multiple types of sentences, and a drawback from one single model won't be taken advantage of. Examples of Human sarcastic comments will be extracted from various social media platforms, in order to cover aspects from people of different age groups and of different fields.
   2)  Take a smaller model first, one of the reasons that could be attributed to the failure of BERT model is that with such a few examples, a model of more than 110M parameters could not be trained properly. Try faster (less parameterized) models such as DistilBert on the dataset and then move on to the complex models such as Bert, RoBERTa, etc.  

#### Qualitative Analysis of Incorrect Labeled Examples:
After testing out quite a few types of human generated sentences, I found that the Bert model is easily able to figure out that the input sentence was generated by a human. Whereas when tested on AI generated sarcastic sentences it showed quite poor performance. Some of the reasons apart from the above specific adversarial examples could be: \\

* The labelling data that was used to train the model had very few instances of AI generated sentences. Though when I created the dataset I purposely made the distribution equal for both the classes. From this we could infer that even humans are unable to correctly distinguish between the 2 types of sentences. This also lead to the fact that model just overfits itself on label 1 and therefore, whatever we give it as an input, it predicts 1 and thereby not having any human labeled sentence to be predicted incorreclty. 

Now let's try to explain why the above examples failed to be correctly labeled by the LLM. In general all of the examples all AI generated sentences which are incorrectly labeled by the model. 

* I can figure out a pattern in the AI generated sentences, that they are always following the grammatical aspects of English Language. For example, the first letter is always capital, making use of expression related words such as Oh, Wow, etc. Sentence - 2,3 and 4
* Another reason which was also present in the feedback by one of the annotators was that it is sometimes complex, it may seem normal to people who are conversing/learning English from a very young age, but in general it is hard to decode the underlying meaning of the sentence. Sentence -3 
* Most of the sentence generated by AI is more often relatable to a working person, and not the old generation or the young generation. For example, sentence 2,3,4 and 5 were more attributed to a person who works and have to travel to the office. Only Sentence 1 can be weakly attributed to a child who has an History exam next day maybe. 

These were some of the aspects present in the current dataset and the adversarial examples that were responsible for the model's poor performance on AI generated sentences. 

#### Error Analysis Sentences:
* Trying to know all this history tonight is gonna kill me
* Wow, thanks for the feedback. I had no idea that my presentation skills were so terrible.#notreally
* Oh great, another meeting. I can't wait to sit through hours of mind-numbing presentations.
* I love sitting in traffic for hours. It gives me so much time to contemplate life's mysteries.
* Oh, I just love filling out paperwork. It's my favorite thing to do on a Friday afternoon.


