# sms_spam_detection
# MSU AI Bootcamp 2023 -2024
# Author
* Taylor Peterson
# Background
>You'll be refactoring code from an SMS text classification solution into a function that constructs a linear Support Vector Classification (SVC) model. Once the model is created and trained, you will create a Gradio app to host the application, enabling users to test text messages. The application will provide feedback to users, indicating whether the text is classified as spam or not, based on the model's performance.
# Files
* In the main branch, these files and directories exist:

* `gradio_sms_text_classification.ipynb` 
    * This file contains the main Gradio interface that connects to the pipeline created from the below file.
* `sms_text_classification_solution.ipynb` 
    * This file builds a Pipeline with the vectorizer and SVM model. It classfies the text and displays the results for the Gradio Interface to output.
* `Resources/SMSSpamCollection.csv`
    * This is the main CSV file that is read into both files. 

# Challenge Instructions
# Create the SMS Classification Function
1. Using the code in the sms_text_classification_solution.ipynb file, create the sms_classification function in the gradio_sms_text_classification.ipynb by doing the following:

    * Set the features variable to the text message column of the DataFrame.

    * Set the target variable to the "label" column of the DataFrame.

    * Split data into training and testing and set the test_size to 33%.

    * Build a pipeline to transform the test set to compare to the training set.

    * Fit the model to the transformed training data and return model.

2.Load the `SMSSpamCollection.csv` into a DataFrame and call the `sms_classification` function with the DataFrame, and set the result to the "`text_clf`" variable.

# Create the SMS Prediction Function
1. Use the sms_prediction function to predict the classification of a new text by doing the following:

    * Create a variable that will hold the prediction of a new text.

    * Use a conditional statement that determines if the text message is "**ham**" or **“spam”**.

        * If the message is “ham”, the function should return the following message: `f'The text message: "{text}", is not spam.'`

        * If the message is spam, the function should return the following message: `f'The text message: "{text}", is spam.'`

# Create the Gradio Interface Application
1. Create a Gradio Interface application that takes a textbox for the inputs and has a textbox for the output. The textboxes should have labels that describe what each textbox contains.

2. Launch the application and provide the URL to share the application (`share=True`)

3. To test, use the following text messages to test your application:
---
```
1. You are a lucky winner of $5000!
2. You won 2 free tickets to the Super Bowl.
3. You won 2 free tickets to the Super Bowl. Text us to claim your prize.
4. Thanks for registering. Text 4343 to receive free updates on medicare.
```
---

# Results: 
1. The text message: "You are a lucky winner of $5000!", is `not spam`.
2. The text message: "You won 2 free tickets to the Super Bowl.", is `spam`.
3. The text message: "You won 2 free tickets to the Super Bowl text us to claim your prize.", is `spam`
4. The text message: "Thanks for registering. Text 4343 to receive free updates on medicare.", is `spam`.

# References
* Module 21 Activity files (Gradio)