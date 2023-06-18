## Complete Code for Tensorflow
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TensorFlowOSSLT.py  

## Project
https://github.com/0Domlightning0/MachineLearningOffical  

## Importing 
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/Importing.py  

# Key pieces 

### Line 18 - 20
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TensorFlowOSSLT.py#L18  

abalone_train = pd.read_csv(
    "https://raw.githubusercontent.com/0Domlightning0/MachineLearningOffical/main/OnlyGr6MathCSVnoNames.csv",
    names=['Enrolment','Latitude','Longitude','PercentageofStudentsWhoseFirstLanguageIsNotEnglish','PercentageofStudentsWhoseFirstLanguageIsNotFrench','PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountry','PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountry','PercentageofStudentsReceivingSpecialEducationServices','PercentageofStudentsIdentifiedasGifted','PercentageofGrade3StudentsAchievingtheProvincialStandardinReading','ChangeinGrade3ReadingAchievementOverThreeYears','PercentageofGrade3StudentsAchievingtheProvincialStandardinWriting','ChangeinGrade3WritingAchievementOverThreeYears','PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematics','ChangeinGrade3MathematicsAchievementOverThreeYears','PercentageofGrade6StudentsAchievingtheProvincialStandardinMathematics'])

- pd stands for pandas 
- .read_csv( "File directory" , names= [ list of all variables ] ) 
- You must include all variables names, in order, including the answer

### Line 26
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TensorFlowOSSLT.py#L26  

abalone_labels = abalone_features.pop('PercentageofGrade6StudentsAchievingtheProvincialStandardinMathematics')

- .pop(" Variable you want to predict) will exract/ "pop out" the variable you are trying to predict

### Line 36-37
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TensorFlowOSSLT.py#L36

abalone_model.compile(loss = tf.keras.losses.MeanSquaredError(),
                      optimizer = tf.keras.optimizers.Adam())

- loss = ![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/f60408bb-303f-4dca-961a-d63c1f838c80)  
- Very prone to outliers, 1 variable off by 10 in a perfect set of 100 means all are off by 1 according to the error

### Line 39 
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TensorFlowOSSLT.py#L39

abalone_model.fit(abalone_features, abalone_labels, epochs=1000)

- abalone_features = data set in a pandas format
- abalone_labels = abalone_features without the prediction variable 
- epochs = number of reiterations (1000 is too much)
