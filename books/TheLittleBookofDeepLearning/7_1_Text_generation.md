[<---   7__Synthesis.md](7__Synthesis.md)         [Зміст](README.md)          [7_2_Image_generation.md    --->](7_2_Image_generation.md) 

## 7.1    Text generation

The standard approach to **text synthesis** is to use an attention-based, **autoregressive model**. The most successful in this domain is the **GPT** [Radford et al., 2018], which we described in [§ 5.3](5_3_Attention_models.md).

The encoding into tokens and the decoding is done with the **BPE tokenizer** (see [§ 3.2](3_2_Autoregressive_models.md)).

When it has been trained on very large datasets, a **Large Language Model** (**LLM**) exhibits extremely powerful properties. Besides the syntactic and grammatical structure of the language, it has to integrate very diverse knowledge, e.g. to predict the word following “The capital of Japan is”, “if water is heated to 100 Celsius degrees it turns into”, or “because her puppy was sick, Jane was”.

This results in particular in the ability to solve **zero-shot prediction**, where no training example is available and the objective is defined in natural language, e.g. “In the following sentences, indicate which ones are aggressive.” More surprisingly, when such a model is put in a statistical context by a “prompt” carefully crafted, it can exhibit abilities for question answering, problem solving, and chain-of-thought that appear eerily close to high-level reasoning [Chowdhery et al., Due to these remarkable capabilities, these models are sometimes referred to as **foundation models** [Bommasani et al., 2021].
