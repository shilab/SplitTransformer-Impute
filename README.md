# SplitTransformer-Impute

This repositry includes the source code for our _SplitTransformer_ framework. This transformer is designed for genotype imputation task. It takes corroupted haplotypes as input and generates highly accurate values for the missing indices. Below you can find the overall workflow of our _SplitTransformer_:

![Overall_view](https://github.com/shilab/SplitTransformer-Impute/blob/main/Overall_view.jpg)

We split the features using a fixed size window into Ex-chunks. Each Ex-chunk, or Extra Chunk, overlaps with neighbouring Ex-Chunks. This way, we make sure that for imputing each feature, attention is applied to all neighbouring features up the some fixed distance.

Our SplitTransformer comes with a novel layer, termed Categorical Embedding (CE). This layer allows us to encode categorical values so that each unique categorical value for each feature ends up with a unqiue embedding vector. Our empirical studies show that using such a layer significantly increases performance metrics, such as accuracy, compared to using a convolutional layer instead, whereas applying Embedding layer direclty to such data is not possible.

