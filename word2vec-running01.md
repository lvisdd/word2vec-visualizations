## Word2Vecの実行方法

### ビルドと実行

#### C実装[Word2Vec](https://code.google.com/archive/p/word2vec/)

> ソースは、SVN -> GitHubに移行されたリポジトリからダウンロードできる。
> https://github.com/svn2github/word2vec

#### ビルドと実行は、2行でOK！

```
make
./demo-word.sh
```

#### シェルスクリプトのソースは、8行（データをダウンロード、解凍、学習、推測） -> 実質4行

```bash:demo-word.sh
if [ ! -e text8 ]; then
    wget http://mattmahoney.net/dc/text8.zip -O text8.gz
    gzip -d text8.gz -f
fi
if [ ! -e vectors.bin ]; then
    time ./word2vec -train text8 -output vectors.bin -cbow 0 -size 200 -window 5 -negative 0 -hs 1 -sample 1e-3 -threads 12 -binary 1
fi
./distance vectors.bin
```

```
# ./distance vectors.bin
Enter word or sentence (EXIT to break): king

Word: king  Position in vocabulary: 187

                                              Word       Cosine distance
------------------------------------------------------------------------
                                               iii              0.651677
                                            aragon              0.641466
                                               son              0.639709
                                            afonso              0.627800
                                         coemperor              0.627733
                                                iv              0.622997
                                               vii              0.617210
                                          burgundy              0.609535
                                          grandson              0.608913
                                            prince              0.606976
                                            anshan              0.602718
                                             queen              0.600487
                                           castile              0.597998
                                              agis              0.597758
                                             kings              0.596500
                                           macedon              0.596402
                                            throne              0.594930
                                          jannaeus              0.591344
                                           alfonso              0.588714
                                         sigismund              0.577732
                                         aquitaine              0.576970
                                             henry              0.576540
                                              viii              0.576064
                                           amalric              0.570706
                                            regent              0.567703
                                           reigned              0.567553
                                          isabella              0.565394
                                           crowned              0.563041
                                                vi              0.561982
                                             reign              0.560168
                                              duke              0.557589
                                         frederick              0.557541
                                         melisende              0.553617
                                          lascaris              0.553020
                                              heir              0.552059
                                             ducas              0.551848
                                           alexius              0.551103
                                      hohenstaufen              0.548002
                                           deposed              0.546269
                                         antiochus              0.544277
Enter word or sentence (EXIT to break):
```
