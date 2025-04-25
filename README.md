The classification report evaluates the performance of the model for each class (-1, 1, 2)
    -1 represents one of the classes in the target variable (POOR performance after injury)
     1 represents another class in the target variable (AVERAGE performance after injury)
     2 represents the third class in the target variable (GOOD performance after injury)

Metrics:
    - Precision measures how many of the predicted instances for a class are actually correct (For class -1 & precision with 0.41, meaning 41% predictions for this class are correct)
        - It answers "Of all the players predicted to be in this class, how many truly belong to it?"

    - Recall measures how many of the actual instances for a class are correctly predicted (For class -1 & reacll with 0.40, meaning the model correctly identified 40% of the actual instances of this class)
        - It answers "Of all the players who truly belong to this class, how many were correctly identified by the model?"

    - F-1 Score is the harmonic mean of precision and recall. It balances the two metrics
    - Support is the number of actual instances (Samples) of each class in the test dataset

    - Accuracy shows 0.41, meaning that the model correctly predicted 41% of the test samples.
    - Macro Average is the unweighted average of the precision, recall, and F1-score across all classes. It treats all classes equally regardless of their support
    - Weight Average is the average of the precision, recall, and F1-score across all classes, weighted by the number of instances (support) in each class.

Code:
    - Feature Selection X includes columns related to player statistics
        - The code extracts features (Name, Team Name, Position, Age, Season, FIFA Rating, Injury Type, Date of Injury, Date of Retrurn, Match1_before_injury_player_rating, and Match3_after_injury_Player_rating)

    - Target Variable Y represents "performance after injury". Continuous values in y are binned into 3 discrete categories (low, medium, high)
        - This feature represents player's post-injury performance (Match3_after_injury_Player_rating)

    - The RandomForestClassifier is trained to predict the performance category (low, medium, high) for each player based on their features

Insights:
    - The overall accuracy of 41% is quite low, reflecting that the model struggles to predict the correct class for most test samples.