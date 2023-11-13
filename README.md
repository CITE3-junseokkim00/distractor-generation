# Distractor Generation

A Word2Vec based on Kowiki dump

### Download dependencies
```
$ pip install -r requirements.txt
```

### Download data

check [here](https://dumps.wikimedia.org/backup-index.html)

### How to run a model
``` bash
# step 0. make directory for train data
mkdir data 
cd data

# step 1. Download the stored wikipedia file to your disk.
wget "https://dumps.wikimedia.org/kowiki/20231101/kowiki-20231101-pages-articles-multistream.xml.bz2"

# step 2. Extract the bz2 file.
bzip2 -d "kowiki-20231101-pages-articles-multistream.xml.bz2"

cd ..

# step 3. Build Corpus.
python build_corpus.py --lcode='ko' --max_corpus_size=1000000

# step 4. make wordvectors
python make_wordvectors.py --lcode='ko' --vector_size=300 --window_size=5 --vocab_size=20000 --num_negative=5
```



Reference: [https://github.com/Kyubyong/wordvectors](https://github.com/Kyubyong/wordvectors)