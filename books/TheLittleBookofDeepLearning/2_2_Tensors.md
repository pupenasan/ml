[<---   2_1_GPUs_TPUs_and_batches.md](2_1_GPUs_TPUs_and_batches.md)         [Зміст](README.md)          [3__Training.md    --->](3__Training.md) 

## 2.2    Tensors

GPUs and **deep learning frameworks** such as Py-Torch or JAX manipulate the quantities to be processed by organizing them as **tensors**, which are series of scalars arranged along several discrete axes. They are elements of $R^{N_1×···×N_D}$ that generalize the notion of vector and matrix.

Tensors are used to represent both the signals to process, the **trainable parameters** of the models, and the intermediate quantities they compute. The latters are called **activations**, in reference to
neuronal activations.

For instance, a time series is naturally encoded as a $T×D$ tensor, or, for historical reasons, as a $D×T$ tensor, where $T$ is its duration and $D$ is the dimension of the feature representation at every time step, often referred to as the number of **channels**. Similarly a 2D-structured signal can be represented as a $D×H×W$ tensor, where $H$ and $W$ are its width and height. An RGB image would correspond to $D=3$, but the number of channels can grow up to several thousands in large models.

Adding more dimensions allows for the representation of series of objects. Fifty RGB images of resolution $32×24$ can, for instance, be encoded as a $50×3×24×32$ tensor

Deep learning libraries all provide a large number of operations that encompass standard linear algebra, complex reshaping and extraction, and deep-learning specific operations, some of which we will see in [Chapter 4](4__Model_components.md). The implementation of tensors separates the shape representation from the storage layout of the coefficients in memory, which allows many reshaping, transposing, and extraction operations to be done without coefficient copying, hence extremely rapidly.

In practice, virtually any computation can be decomposed into elementary tensor operations, which avoids non-parallel loops at the language level and poor memory management.

Besides being convenient tools, tensors are instrumental to achieve computational efficiency. All the people involved in the development of an operational deep model, from the designers of the drivers, libraries, and models to those of the computers and chips, know that the data will be manipulated as tensors. The resulting constraints on locality and block decomposability enable all the actors in this chain to come up with optimal designs.