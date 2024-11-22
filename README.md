# Detection of Flaky Tests with Fine-tuned LLM

## Raw Data Files (All Created by Go_Through_IPFlakies.ipynb)
- selected_methods.csv: all accessible test methods in iPFlakies dataset
  - Row: corresponding row number in https://sites.google.com/view/ipflakies (1-index)
  - Project_Name: name of the project with the test method
  - URL: URL to the python code file with the test method
  - Class: class of the test method
  - Test: test method name
  - Content: test method
  - Detected: whether the test method is detected as flaky
- data: data needed for testing 10 projects
  - For each project _p_:
    - test_set.jsonl: containing all the test methods of _p_
    - training_set.jsonl and validation_set.jsonl: constructed from test methods of the other 9 projects

## Notebooks
- Go_Through_IFixFlakies.ipynb: creating raw data files
- Naive_GPT_4o_mini.ipynb: predicting test methods in test_set.jsonl by naive GPT-4o-mini
- Finetuned_GPT_4o_mini.ipynb: predicting test methods in test_set.jsonl by finetuned GPT-4o-mini, finetuning by training_set.jsonl and validation_set.jsonl
