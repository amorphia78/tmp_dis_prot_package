# tmp_dis_prot_package 

## Temporary staging point repo

THIS REPO IS NOT USEFUL TO ANYONE EXCEPT ME FOR TESTING PURPOSES. THERE WILL BE A NEW PUBLIC REPO FOR THE SAME PURPOSE.

## TODO

* BEN: Transfer the article production document from Google Doc into [full_article_sampling_and_production_details](/doc/full_article_sampling_and_production_details.md).
* BEN: Think about how to include "the other (trivial) analysis code that does things like Fishers exact test for for article prep document" (as per other TODO).
* BOTH: Think about what else needs to be here.

## Contents

### [/articles/](/articles/)

Contains all 110 articles, in [specific](/articles/specific) (100) and [general](/articles/general) (10) subdirectories, in HTML format, produced as described in [full_article_sampling_and_production_details](/doc/full_article_sampling_and_production_details.md).

### [/src/word_count/](/src/word_count/) and [/word_count/](/word_count/)

Running [/src/word_count/code_and_count_article_words.py](/src/word_count/code_and_count_article_words.py) will process the specific articles recreate the word count output files in [/word_count/](/word_count/), also using additional files, as documented in [article_word_count_details](/doc/article_word_count_details.md).

### [/llm_caches/](/llm_caches/)

Contains caches LLM prompt responses so that [code_and_count_article_words.py](/src/word_count/code_and_count_article_words.py) can be run by those without an Anthropic API key, using the [process_with_cache()](/src/word_count/llmproc_core.py#L60) function.

### [/experiment/](/experiment/)

Contains .R files and data to produce the analyses in the main text (`experiment_analyses.R`) and the appendices (`appendix_analyses.R`), respectively. Data from the experiment (all wave 1 respondents) are in the file `disruption_stimulus_data_clean.RData` (and also in `disruption_stimulus_data_clean.csv` for easier visual inspection/import into other statistical software. The file `all_ratings_clean.csv` contains the ratings of the articles produced by research assistants, crowd coders and an LLM.

The R scripts `load_and_join_data.R` and `functions.R` are called by the analysis scripts above and contain helper code respectively for cleaning the data (including joining experiment and rating data) and for analyzing and plotting results. `raking/twoway_frequencies_IAS.Rdata` contains the two-way joint distributions of ideology, age and sex in the UK population that are necessary to rake their full joint distribution, which is necessary for representativeness weighting.

The Figures and Tables folders contain the graphs and LaTeX tables produced by the analysis scripts. These are the figures and tables that appear in the main text and appendices of the paper.

### [/doc/](/doc/)

Contains documentation files linked to above, including details on article sampling and production, results of two pilot tests for rating characteristics, and a priori power analyses.
