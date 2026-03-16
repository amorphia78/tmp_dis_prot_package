# tmp_dis_prot_package 

## Temporary staging point repo

The plan is to assemble everything here, then we make a new repo (probably called dis_prot_package) and just copy this one into it so that it is the same, but we lose the commit history, which is unnecessary for this purpose.

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

Contains .R files and data to produce the analyses in the main text (`experiment_analyses.R`) and the appendices (`appendix_analyses.R`), respectively. Data from the experiment (all wave 1 respondents) are in the file `disruption_stimulus_data_clean.RData` (and also in `disruption_stimulus_data_clean.csv` for easier visual inspection/import into other statistical software. The Figures and Tables folders contain the graphs and LaTeX tables produced by the analysis script above. These are the figures and tables that appear in the main text and appendices of the paper.

### [/doc/](/doc/)

Contains documentation files linked to above, including details on article sampling and production, results of two pilot tests for rating characteristics, and a priori power analyses.
