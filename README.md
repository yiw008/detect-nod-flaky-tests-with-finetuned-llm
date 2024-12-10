# Evaluating Fine-tuned Generative LLM on Detection of Flaky Tests

## Raw Data Files (All Created by Go_Through_IPFlakies.ipynb)
- all_test_methods.csv: all accessible test methods in the iPFlakies dataset
- selected_methods.csv: test methods of 10 selected projects in the iPFlakies dataset
- refined_selected_methods.csv: test methods of 10 selected projects in iPFlakies dataset & test methods of 10 selected projects not recorded in iPFlakies dataset (assumed as non-flaky tests)
  - Row: corresponding row number in https://sites.google.com/view/ipflakies (1-index)
    - -1: augmented when grabbing assumed non-flaky tests not recorded in the iPFlakies dataset
  - Project_Name: name of the project with the test method
  - URL: URL to the Python code file with the test method (usually copied from the iPFlakies dataset)
  - New URL: URL to the raw Python code file with the exact test method (so we can directly extract the test code from this URL)
  - Class: class of the test method
  - Test: test method name
  - Content: test method
  - Detected: whether the test method is detected as flaky
- data: data needed for testing 10 projects
  - For each project _p_:
    - test_set.jsonl: containing all the test methods of _p_
    - training_set.jsonl: constructed from test methods in the other 9 projects (balanced after random oversampling)

## Notebooks
- Go_Through_IFixFlakies.ipynb: creating raw data files
- Naive_GPT_4o_mini.ipynb: predicting test methods in test_set.jsonl by naive GPT-4o mini
- Finetuned_GPT_4o_mini.ipynb: finetuning GPT-4o mini with training_set.jsonl & predicting test methods in test_set.jsonl by finetuned GPT-4o mini
