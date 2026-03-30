
PART B SUMMARY
==============
Best Advanced MLP Configuration:
{'hidden_units': (512, 256, 128), 'dropout_rates': (0.3, 0.2, 0.1), 'learning_rate': 0.001, 'l2_lambda': 0.0001, 'batch_size': 128}

Final Tuned Advanced MLP Results:
Validation Accuracy  : 0.9974
Validation Macro F1  : 0.9974
Test Accuracy        : 0.9967
Test Macro F1        : 0.9967
Test Precision       : 0.9967
Test Recall          : 0.9967

Confidence / Ambiguity:
Low-confidence threshold : 0.90
Low-confidence samples   : 92 / 8777 (1.05%)
Total incorrect          : 29
Errors flagged           : 24
Error capture rate       : 82.76%

Class-level findings:
Hardest class by F1  : Class 5
Easiest class by F1  : Class 10
