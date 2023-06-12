# deep-learning-challenge
Background

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, we have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

    EIN and NAME—Identification columns
    APPLICATION_TYPE—Alphabet Soup application type
    AFFILIATION—Affiliated sector of industry
    CLASSIFICATION—Government organization classification
    USE_CASE—Use case for funding
    ORGANIZATION—Organization type
    STATUS—Active status
    INCOME_AMT—Income classification
    SPECIAL_CONSIDERATIONS—Special considerations for application
    ASK_AMT—Funding amount requested
    IS_SUCCESSFUL—Was the money used effectively

Data Processing

The "IS_SUCCESSFUL" column is the target variable, as this notes whether the funding  was successful (1) or not (0). Feature Variables: The data hasseveral feature variables, including "APPLICATION_TYPE," "AFFILIATION," "CLASSIFICATION," "USE_CASE," "ORGANIZATION," "STATUS," "INCOME_AMT," and "SPECIAL_CONSIDERATIONS." For the original model the fields "EIN" and "NAME" were removed from the data as they are idenitifiers and not used for modeling.

Initial Model
Factors:
Removed EIN, Name, and Special Considerations columns
Application types with <1000 applications were grouped in Other.
Added a step to only use rows where the Classification value >1.
Classification types <100 grouped into Other.
Two hidden layers with 80 and 30 neurons.
Epochs=20.
Results
Loss: 0.5512855052947998, Accuracy: 0.7345772385597229
Close to the target accuracy, but loss is larger than we would want.

Optimization 1
Factors:
Removed EIN, Name, and Special Considerations columns
Application types with <700 applications were grouped in Other.
Added a step to only use rows where the Classification value >1.
Classification types <200 grouped into Other.
Three hidden layers each with 80 neurons.
Epochs=30.
Results
Loss: 0.5757166147232056, Accuracy: 0.7271137237548828
Worse on both values

Optimization 2
Factors:
Removed all non-numerical columns except for Application Type and Classification
Application types with <1100 applications were grouped in Other.
Added a step to only use rows where the Classification value >1.
Classification types <1000 grouped into Other.
Three hidden layers with 80-30-30 neurons.
Epochs=30.
Results
Loss: 0.6510111689567566, Accuracy: 0.6090962290763855
Worse on both values

Results
None of the models were very successful. Next steps would be to try a different type of model, such as Random Forest or SVM.



