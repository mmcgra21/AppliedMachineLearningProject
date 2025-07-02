# Home Credit - Credit Risk Modeling

## File Hierarchy

```text
.
├── AML_Project_Data_Preprocessing.ipynb                    # Preprocess datasets
├── AML_Project_Model_Training.ipynb                        # Train models
├── AML_Project_Model_Prediction_and_Evaluation.ipynb       # Predict and evaluate trained models
├── home-credit-default-risk                                # Data folder
│   ├── correlation_matrices        # Precomputed correlation matrices used in model training
│   │   └── ...
│   ├── train_val_data              # Pre-split development and test data
│   │   └── ...
│   ├── models                      # Saved pre-trained models
│   │   └── ...
│   ├── transformed                 # Preprocessed supplementary datasets
│   │   └── ...
│   ├── application_train.csv       # Original main dataset
│   ├── POS_CASH_balance.csv        # Original supplementary dataset #1
│   ├── credit_card_balance.csv     # Original supplementary dataset #2
│   ├── previous_application.csv       # Original supplementary dataset #3
│   ├── bureau.csv                  # Original supplementary dataset #4
│   ├── bureau_balance.csv          # Original supplementary dataset #5
│   └── installments_payments.csv   # Original supplementary dataset #6
└── README.md
```

## How to run code

Steps to run code:

1. Run `AML_Project_Data_Preprocessing.ipynb`: This will first split the `application_train.csv` into training and test datasets and save them into the `train_val_data` directory. Then it will preprocess the original supplementary datasets and save new transformed datasets into the `transformed` directory.
2. Run `AML_Project_Model_Training.ipynb`: This will access the `train_val_data` and `transformed` directories and train any model that the user chooses to specify in the "Define model and search space" section of the notebook. This is an easy way to try different types of models in a user friendly type of way. The code will create and use the `correlation_matrices` directory to store precomputed correlation matrices of the datasets to make training faster and it will also create the `models` directory to store *.pickle* files of the models trained so that you do not have to redo training and can instead just load the model from the `models` directory.
3. Finally, run `AML_Project_Model_Prediction_and_Evaluation`: This contains the code used to make a prediction with the multiple models trained per dataset. It also has a function to easily evaluate any trained model in the `models` directory so you can compare performance between models. The code computes the AUROC scores on the test data. It also has code to plot the ROC curves of selected models in the `models` directory.

## Submission

Note that before submitting, we have run the code and created the preprocessed data, correlation matrices, and trained a bunch of models. So these files are already created and saved in their respective directories. Therefore you can start on any step in the "How to run code" section.
