[<---   2_2_Tensors.md](2_2_Tensors.md)         [Зміст](README.md)          [3_1_Losses.md    --->](3_1_Losses.md) 

# Chapter 3 Training

As introduced in [§ 1.1](1_1_Learning_from_data.md), training a model consists of minimizing a loss $\mathscr{L}(w)$ which reflects the performance of the predictor $f(\cdot;w)$ on a **training set** $\mathscr{D}$. Since the models are usually extremely complex, and their performance is directly related to how well the loss is minimized, this minimization is a key challenge, which involves both computational and mathematical difficulties.