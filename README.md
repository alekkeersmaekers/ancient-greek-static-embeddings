# Static embeddings (type vectors) for Ancient Greek

Static embeddings (type vectors) for Ancient Greek, created as follows:
* For a given target lemma, all context lemmas that have a direct syntactic dependency relation with the target lemma in the [GLAUx corpus](https://github.com/alekkeersmaekers/glaux) are extracted, the dependency type is specified (head, child or coordinating), and the concatenation of dependency type + context lemma is counted. See [this paper](https://doi.org/10.53482/2023_55_410) for more details.
* A PPMI transformation is applied to the co-occurence matrix, using smoothed context counts as described in [Levy et al. 2015, Improving Distributional Similarity
with Lessons Learned from Word Embeddings](https://doi.org/10.1162/tacl_a_00134).
* The matrix is reduced to 300 dimensions through Singular Value Decomposition, multiplying the U-matrix with the square root of the Σ-matrix (see again [Levy et al. 2015](https://doi.org/10.1162/tacl_a_00134)).

These embeddings will be updated whenever I make progress at the computational modeling of Ancient Greek semantics or the GLAUx corpus grows.

Currently two files are provided, offering embeddings for nouns only and all words. In my experience, the embeddings seem to work a little better when they are restricted to a specific word class.

The code to generate such embeddings will be released in the [GLAUx NLP](https://github.com/alekkeersmaekers/glaux-nlp) repository in the near future.

# How to cite

If you make use of these embeddings, please cite the following paper:

> Keersmaekers, A.; Speelman, D.; 2023. [Applying Distributional Semantic Models to a Historical Corpus of a Highly Inflected Language: the Case of Ancient Greek](https://doi.org/10.53482/2023_55_410). Glottometrics; 2023; Vol. 55; pp. 17 - 43.

Please note that the techniques used here are somewhat updated from the original paper, as described above. If you want to use the original embeddings used in this study, please use the data from [this repository](https://github.com/alekkeersmaekers/greek-count-vectors) instead.

# License

Al data is available under a [CC BY-SA 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/).
