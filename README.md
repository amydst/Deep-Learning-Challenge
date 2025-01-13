# Deep-Learning-Challenge

## Overview:
This neural network model is designed to predict the success of a venture Alphabet Soup gave funding to, based on several features. The optimized model obtained a 75.06% accuracy at predicting the success of the project.


## Results: 
### Preprocessing the data:
- The target variable is called 'IS_SUCCESSFUL' Meaning the binary clasification of the project as succesful at reaching its goal or not.
-The features of the optimized model are:
  - Name: Categorized by the kind of group or organization included in their name (ex. Association, Club, Ministry, etc.)
  - Affiliation:
  - Classification: Categories with more than 100 counts, any category under 100 uses was combined into "Other" Category
  - Application Type: Type used more 10 or more time, all other types were combined into "Other"
  - Income Amount:  Divided into two categories: No income ($0) or Has income ('Greater than 0')
  - Ask Amount: This category has a really wide range, so it was grouped into 21 categories:
            "0 - 5,000",
            "5,001 - 450,000",
            "450,001 - 900,000",
            "900,001 - 1,350,000",
            "1,350,001 - 1,800,000",
            "1,800,001 - 2,250,000",
            "2,250,001 - 2,700,000",
            "2,700,001 - 3,150,000",
            "3,150,001 - 3,600,000",
            "3,600,001 - 4,050,000",
            "4,050,001 - 4,500,000",
            "4,500,001 - 4,950,000",
            "4,950,001 - 5,400,000",
            "5,400,001 - 5,850,000",
            "5,850,001 - 6,300,000",
            "6,300,001 - 6,750,000",
            "6,750,001 - 7,200,000",
            "7,200,001 - 7,650,000",
            "7,650,001 - 8,100,000",
            "8,100,001 - 8,550,000",
            "over 8,550,000 "
  - Special Considerations: If the application had special considerations or not, 1 for yes, 0 for not.
    The following columns were removed because they did not add to the accuracy of the model: 'EIN'and'STATUS',

### Compiling, Training, and Evaluating the Model
- The model has 3 layers plus the output layer, first one has 64 nodes, the second and third layers have 32 nodes each, all using the Tanh activation function.
    These specifications were selected as they improved the accuracy of the model.
- The model achieve the target performance of 75%, this was achieved by adding another hidden layer and more nodes to all layers, in addition to some extra processing of the data:
        - Ask Amount was converted into a categorical variable
        - Name was included and transformed into categories based on the types of grops in the name of the organization. This is the change that contributed the most to the improvement of the model.
        - Status was removed since it didn't contribute to the model
        - Income Amount was also converted into a categorical variable, dividing the projects if they had reported income or not. 

## Summary: 
Overall, the model achieved a great accuracy level of 75% with the performed optimization, from the various steps taken to improve performance it was noted that the range of values of some of the features might be to wide and its ocurrences are too variable for the model, it could prove useful to separate the data into subsets by 'Ask Amount' and 'Income Amount'. 

Another suggestion would be to include more categories of the organizations based on their Names, there are 19,146 in the 'Other' category, it's possible that some of them can be taken out into their own category and help improve the model.
