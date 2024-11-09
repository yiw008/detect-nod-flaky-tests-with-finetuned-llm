# Detection of Flaky Tests with Fine-tuned LLM

## Raw Data Files (All Created by Go_Through_IPFlakies.ipynb)
- all_test_methods.csv: all accessible test methods in iPFlakies dataset
  - Row: corresponding row number in https://sites.google.com/view/ipflakies (1-index)
  - URL: URL to the python code file with the test method
  - Class: class of the test method
  - Test: test method name
  - Content: test method
  - Detected: whether the test method is detected as flaky
- training_set.jsonl: un-balanced training set
- balanced_training_set.jsonl: balanced training set by random undersampling
- validation_set.jsonl: un-balanced validation set
- balanced_validation_set.jsonl: balanced validation set by random undersampling
- test_set.jsonl: test set

## Notebooks
- Go_Through_IFixFlakies.ipynb: creating raw data files
- Naive_GPT_4o_mini.ipynb: predicting test methods in test_set.jsonl by naive GPT-4o-mini
- Finetuned_GPT_4o_mini_without_Random_Undersampling.ipynb: predicting test methods in test_set.jsonl by finetuned GPT-4o-mini, finetuning by training_set.jsonl and validation_set.jsonl
- Finetuned_GPT_4o_mini_with_Random_Undersampling.ipynb: predicting test methods in test_set.jsonl by finetuned GPT-4o-mini, finetuning by balanced_training_set.jsonl and balanced_validation_set.jsonl
