# Turkish-NLP-preprocessing-module
NLP Preprocessing module for Turkish language

Consists of:
- Morphological Analyzer/Disambiguator
- Normalizer
- Sentence Splitter
- Stopword Remover
- Tokenizer

#### ------------------------------------------------------------------------------------------------

**Morphological Analysis**
- Lemmatization

**Normalization:**
- Removes punctuations
- Lowercase
- Converts numbers to word form
- Removes accent marks
- Spelling/typo correction
    - pre-defined typos lexicon
    - Levenshtein distance
    
**Sentence Splitting**

**Stopwords:**
- Static
- Dynamic
    - frequent words
    - rare words

**Tokenization**

#### ------------------------------------------------------------------------------------------------

**Recently DONE**:
- Tokenizer removes extra whitespaces
- detect_rare_words flag of Normalizer is updated and is now a more flexible, integer argument.
- Documentation is improved:
    - Doc-strings are updated with Typing
    - Readme.md file is expanded with details, DONE, TODO, Potential improvements and resources
- Replace print statements with logging
- Find a better Tokenizer:
    - TrTokenizer:
        - Doc and source: https://github.com/apdullahyayik/TrTokenizer
        - Replaced our CMPE561 implementation with this for now. But there's a chance our implementation is better.
        - Drops characters like $ # €.
        - We can decide to continue with this one or not in future according to custom needs.
        
    - NLTK:
        - Doc: https://www.nltk.org/api/nltk.tokenize.html
        - Contains a variety of Tokenizers: Tweet, MWE, Punct, etc
        - Easy to use with simple Import
        
    - Spacy:
        - Doc: https://spacy.io/api/tokenizer
        - Sample code: https://machinelearningknowledge.ai/complete-guide-to-spacy-tokenizer-with-examples/
        - Contains TR language support, but did not even handle multi-whitespace. No reason to use this for now.
- Create requirements.txt

**TODO:**
- Expand lexicons

**Potential improvements:**
- Named Entity Recognition:
    - Person, Location, Number, Date
    - Remove HTML: convert it to <HTML_LINK> token
    - Remove URLs: convert it to <URL> token
    - Remove Emoji and Emoticon: convert to <EMO> token
        - good emoticon replacer with positive and negative sentiments: https://www.kaggle.com/egebasturk1/yemeksepeti-sentiment-analysis
- Expand abbreviations (Vowelizer): e.g "mrb" -> "merhaba"
    - it is mentioned in https://aclanthology.org/E14-2001.pdf
- Remove duplicate characters: e.g "yeemeeeeek haaarikaydııı" -> "yemek harikaydı"
- Syllabication: e.g "unutmadım" -> ["u", "nut", "ma", "dım"]
    - Can be useful for syllable-level models
- Remove strings with len less than 2/3 (can be added optionally to Normalizer)
- Noise removal (optional and depends on context e.g html tags, twitter hashtags, etc)
    
    
**Some nice resources that can be used to improve our tool:**
- https://github.com/topics/turkish-nlp
- https://pypi.org/project/spark-nlp/
- https://github.com/MeteHanC/turkishnlp