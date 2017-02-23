## Word2Vecの実行方法

### 引数のチューニング

#### 難しい理論は、引数のチューニングでOK！

```
C:\work\word2vec-win32>word2vec
WORD VECTOR estimation toolkit v 0.1b

Options:
Parameters for training:
        -train <file>
                Use text data from <file> to train the model
        -output <file>
                Use <file> to save the resulting word vectors / word clusters
        -size <int>
                Set size of word vectors; default is 100
        -window <int>
                Set max skip length between words; default is 5
        -sample <float>
                Set threshold for occurrence of words. Those that appear with higher frequency in the training data will be randomly down-sampled; default is 0 (off), useful value is 1e-5
        -hs <int>
                Use Hierarchical Softmax; default is 1 (0 = not used)
        -negative <int>
                Number of negative examples; default is 0, common values are 5 - 10 (0 = not used)
        -threads <int>
                Use <int> threads (default 1)
        -min-count <int>
                This will discard words that appear less than <int> times; default is 5
        -alpha <float>
                Set the starting learning rate; default is 0.025
        -classes <int>
                Output word classes rather than word vectors; default number of classes is 0 (vectors are written)
        -debug <int>
                Set the debug mode (default = 2 = more info during training)
        -binary <int>
                Save the resulting vectors in binary moded; default is 0 (off)
        -save-vocab <file>
                The vocabulary will be saved to <file>
        -read-vocab <file>
                The vocabulary will be read from <file>, not constructed from the training data
        -cbow <int>
                Use the continuous bag of words model; default is 0 (skip-gram model)

Examples:
./word2vec -train data.txt -output vec.txt -debug 2 -size 200 -window 5 -sample 1e-4 -negative 5 -hs 0 -binary 0 -cbow 1


C:\work\word2vec-win32>
```
