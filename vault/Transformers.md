a neural network architecture that surprisingly generalizes to many domains

Model architecture diagram: https://ar5iv.labs.arxiv.org/html/1706.03762

Components
* Tokens - splitting text into bite size pieces for model to consume, can be by character (nanogpt tutorial), by sub word (industry)
* Encoder - maps tokens to integers using [[Hashmap]]
* Decoder - maps predictions into tokens using [[Hashmap]]
* Input Embedding - a float representation of words into lower dimension
* Positional encoding
	* a representation of the word location in the sentence. Transformers did circular wiggle, where embedding of the word was perturbed around it in a circle where each angle represents if word occurs first or occurs last in the sentence
* Multi-Head Attention
	* Attention - Weighting words around 1 word based on how important those words are to understanding what the 1 word means
	* Multi-head - because softmax considers only one candidate word, useful to consider many
* Feed forward - calculate nn intermediate output as sum product of weights and biases
* Add & Norm - [[Skip connections]]
- Masked Multi-Head
	* Masking - force the unhelpful features to zero, like a filter
* Linear
* [[Softmax]]


References

Visualization by the Financial Times
https://ig.ft.com/generative-ai/

Intro to Transformers by Andrej Karpathy
https://www.youtube.com/watch?v=XfpMkf4rD6E

Transformers summary - key papers google zurich
https://www.linkedin.com/posts/sanyambhutani_incredible-summary-of-the-transformer-architecture-activity-7071116937103089664-8iow

Transformers by hand analytic
https://www.linkedin.com/posts/eric-vyacheslav-156273169_transformer-by-hand-one-of-the-best-exercise-activity-7209571085837594625-UxEM?utm_source=share&utm_medium=member_android

LLM robotics - has transformers from scratch by brandon rohrer
https://github.com/jrin771/Everything-LLMs-And-Robotics/tree/main#llms-educational-resources-

Transformers from scratch
https://e2eml.school/transformers.html

Transformers from scratch pytorch kaggle notebook [https://www.linkedin.com/feed/update/urn:li:activity:7148379049566900224?utm_source=share&utm_medium=member_android](https://www.linkedin.com/feed/update/urn:li:activity:7148379049566900224?utm_source=share&utm_medium=member_android)

Attention is all you need

Transformers interpretability
https://transformer-circuits.pub/2021/framework/index.html

