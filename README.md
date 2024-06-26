# Early_Disease_Detection_NLP_Model

## By Team 28: 
- Adepu Ashvith
- Aryan Toshniwal
- Bhavesh Kumar Raktani
- Param Shah  


## Demo Picture:  

![image](https://github.com/BlackHorseFTW/Early_Disease_Detection_NLP_Model/assets/92382507/257ef9e6-c930-44ef-84be-6804279d59c5)

## Problem Statement
NLP can assist in identifying early signs and symptoms of diseases by analyzing patient descriptions or medical reports, potentially leading to earlier diagnosis and treatment.
## Motivation
- Enhanced Diagnostic Accuracy: Traditional diagnostic methods heavily rely on the expertise and availability of healthcare professionals, which can vary widely. Our NLP model leverages advanced algorithms to analyze patient descriptions and identify patterns indicative of early-stage diseases. By doing so, it reduces the likelihood of misdiagnosis and ensures that patients receive the correct treatment promptly.
- Increased Accessibility: In many regions, especially in rural and underserved areas, access to specialized healthcare is limited. Our NLP model can bridge this gap by providing a reliable diagnostic tool that can be accessed remotely. Patients can describe their symptoms through a simple interface, and the model will process this information to suggest possible diseases, thereby democratizing access to healthcare.
- Time and Cost Efficiency: Early detection often involves numerous tests and consultations, which can be time-consuming and expensive. Our NLP model streamlines this process by quickly analyzing symptoms and narrowing down potential diagnoses. This not only saves time for both patients and healthcare providers but also reduces the overall costs associated with extensive diagnostic procedures.
- Proactive Healthcare: The ability to detect diseases early means that interventions can be made before conditions worsen. This proactive approach to healthcare can lead to better disease management, reduced progression of illnesses, and ultimately, better patient prognoses. By identifying diseases at an early stage, our NLP model empowers patients and healthcare providers to take timely action.
## Approach
Approach to Building a Disease Prediction Model
## 1. Data Preparation
- Loaded Data: The CSV file containing disease data was read into a Pandas DataFrame.
- Mapped Diseases to Numerical Values: A dictionary was created to map each disease name to a unique numerical value, and the DataFrame was updated accordingly.
- Extracted Unique Symptom Words: All unique symptom words were identified and collected from the symptom columns.
- Encoded Symptoms into Binary Features:
A new DataFrame was created with binary columns for each unique symptom word.
The binary columns were populated based on the presence of symptoms in the original data.
- Saved Encoded DataFrame: The transformed DataFrame was stored into a new CSV file.
## 2. Model Training
- Split Data into Features and Labels: The encoded DataFrame was separated into feature columns (symptoms) and labels (diseases).
- Split Data into Training and Testing Sets: The data was divided into training and testing subsets (typically 80% for training and 20% for testing).

### Defined the Neural Network Model:

- Sequential Model: A linear stack of layers was created.

- Input Layer:
A Dense layer with 128 neurons and relu activation was added to handle the input features.
- Dropout Layer (50%): Helped prevent overfitting by randomly setting half of the input units to 0 at each update during training.
- Hidden Layer:
Another Dense layer with 64 neurons and relu activation was added to provide an intermediate level of abstraction.
- Dropout Layer (50%): Another dropout layer was added to further prevent overfitting.
- Output Layer:
A Dense layer with the number of neurons equal to the number of unique diseases was added, using the softmax activation function to output a probability distribution over the classes.
### Compiled the Model:

- The loss was set to sparse_categorical_crossentropy, which is suitable for integer-labeled multi-class classification.
- The adam optimizer was chosen, which adjusts the learning rate throughout training.
- Accuracy was set as the metric to evaluate the model’s performance.
### Trained the Model:

The model was trained using the fit method with training data (X_train, y_train), specifying the number of epochs, batch size, and validation data (X_test, y_test).
The model trained over multiple epochs, adjusting weights to minimize the loss.
Saved the Trained Model: The trained model was saved to a file (disease_prediction_model.h5) to allow for future use without retraining.

## 3. Prediction
Loaded the Trained Model: The saved model was loaded from the file.
- Preprocessed Input Text:
The input text symptoms were converted into a binary vector representing the presence of each symptom.
Created Reverse Disease Mapping: A dictionary was generated to map numerical values back to disease names.
- Predicted the Disease:
The model was used to predict the disease based on the input symptom vector.
The predicted disease and the confidence level of the prediction were determined.
Ran Predictions for Test Inputs: Iterated through test inputs, predicted diseases, and printed the results with confidence levels.
## Results
The model predicts diseases based on the symptoms provided in the input text. Here's an explanation of the output and what it represents:

### Input Text:

This is the description of symptoms provided by the user. The model processes this text to identify relevant symptoms and predict the possible disease.
### Predicted Disease:

This is the disease that the model predicts based on the symptoms mentioned in the input text. The prediction is made by comparing the input symptoms with patterns learned from the training data.
### Confidence Score:

The confidence score represents the model's certainty in its prediction. It is a value between 0 and 1, where a higher score indicates greater confidence in the predicted disease.
For instance, a confidence score of 0.85 means the model is 85% certain that the predicted disease matches the input symptoms.
## Example Outputs
Input: "Patient has itching, skin rash, nodal skin eruptions, and dischromic patches."

- Predicted Disease: Fungal infection
- Confidence: 1.00

Input: "The patient reports constant back pain and weakness in their limbs. They also experience neck pain, dizziness, and a loss of balance. Alongside these symptoms, they have noticed stiffness in their neck and pain during bowel movements."

- Predicted Disease: Arthritis
- Confidence: 0.99

Input: "The patient has a persistent cough, high fever, and breathlessness. They also report chest pain and fatigue. Additionally, they have noticed phlegm and sweating, along with a loss of appetite and chills."

- Predicted Disease: Peptic Ulcer Disease
- Confidence: 0.22
  
Input: "The patient complains of muscle weakness, joint pain, and fatigue. They also have a skin rash and small dents in their nails. Recently, they have been experiencing weight gain, mood swings, and a constant feeling of hunger."

- Predicted Disease: Osteoarthristis
- Confidence: 0.41
  
These examples illustrate how the model processes symptom descriptions to predict diseases and provides a confidence score to indicate the reliability of each prediction.

## Conclusion
In conclusion, our disease prediction model effectively analyzes input symptoms to predict possible diseases and provides confidence scores to indicate the reliability of each prediction. By leveraging neural network technology and a comprehensive dataset, the model demonstrates promising accuracy in diagnosing various medical conditions. With its user-friendly interface and interpretable outputs, our model offers valuable insights for healthcare professionals and individuals seeking preliminary assessments of their health concerns. As we continue to refine and expand our model's capabilities, we aim to enhance its utility in facilitating early detection and personalized healthcare management


### Acknowledgements

[![Kaggle](https://img.shields.io/badge/Kaggle-Data-blue?style=for-the-badge&logo=kaggle)](https://www.kaggle.com/datasets/itachi9604/disease-symptom-description-dataset?select=dataset.csv)
- **Disease Symptom Description Dataset**


[![Columbia University](https://img.shields.io/badge/Columbia_University-Database-blue?style=for-the-badge&logo=columbia-university)](https://people.dbmi.columbia.edu/~friedma/Projects/DiseaseSymptomKB/index.html) 
- **Disease Symptom Knowledge Base**


[![Nature](https://img.shields.io/badge/Nature-Article-blue?style=for-the-badge&logo=nature)](https://www.nature.com/articles/s41598-023-35482-0) 
- **Scientific Reports**


[![YouTube](https://img.shields.io/badge/YouTube-Video-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/watch?v=kk762SkWv4U)
- **YouTube Video**


[![UpGrad](https://img.shields.io/badge/UpGrad-Blog-red?style=for-the-badge&logo=upgrad)](https://www.upgrad.com/blog/classification-model-using-artificial-neural-networks/)
- **UpGrad Blog**
