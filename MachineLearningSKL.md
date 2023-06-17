### Code for SKL
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py

### Project 
https://github.com/0Domlightning0/MachineLearningOffical

### Useful programs to gain understanding again
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TestingTheTensorWebsite.py  
- Free example on the tensorflow website to find the age of clam shells

https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TestingMachineLearning.py
- Simple tensorflow example

### Importing
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/Importing.py

## Key pieces

### Line18
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L18  

list_of_variables = ['Enrolment',"Latitude","Longitude","PercentageofStudentsWhoseFirstLanguageIsNotEnglish","PercentageofStudentsWhoseFirstLanguageIsNotFrench","PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountry","PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountry","PercentageofStudentsReceivingSpecialEducationServices","PercentageofStudentsIdentifiedasGifted","PercentageofGrade3StudentsAchievingtheProvincialStandardinReading","ChangeinGrade3ReadingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinWriting","ChangeinGrade3WritingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematics","ChangeinGrade3MathematicsAchievementOverThreeYears"]

- This is a list of all your variables, very useful for copy and pasting into code 
- Also used for indexing

## Getting rid of empty data

- Empty data in machine learning will most likely crash the proram (not 0, literally no number)  

### Line 34
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L34  

df.Longitude.median() 
- .median() will calculate the median of all the avalable data in the column
- df stands for dataframe 
- Longitude is the name of your variable 

### Line 36
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L36  

df.Longitude = df.Longitude.fillna(df.Longitude.median())
- .fillna will replace all empty data with what you put in the bracket
- in this case the value you are inputing is the median you calculated before 
- You will have to repeat this for every. single. variable.

### Simple solution
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/MeaninglessCSV.csv  

- If your data file is a CSV, you can Cntrl + F inside of the raw file ",,"
- Since data is seperated by commas (Comma Seperated Values... wow) a double comma must indicate that there is no value seperating the comma -> 
![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/ba005ef8-0e77-40cb-835c-e2d4a4909c2f)
- To find missing data on the edge (don't forget about that PLEASE) search ", "
- This will show a comma led by nothing -> ![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/258ae1ce-f066-4ebe-9c13-e6e1cbd0f84b)
- Do the same process wil " ,"

## Creating the model

### Line 83
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L83   

reg = linear_model.LinearRegression()
- This will call upon the SKLearn linear regression model it is quite good at picking out patterns as it shows amazing resaults with a perfect dataset with perfect data as shown with the simple program  
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TestingTheScore.py
- Use this as a simple frame of the SKLearn model, without the 7000 different measurments and addatives in the actual code

### Line 84
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L84  

reg.fit(df[['Enrolment',"Latitude","Longitude","PercentageofStudentsWhoseFirstLanguageIsNotEnglish","PercentageofStudentsWhoseFirstLanguageIsNotFrench","PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountry","PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountry","PercentageofStudentsReceivingSpecialEducationServices","PercentageofStudentsIdentifiedasGifted","PercentageofGrade3StudentsAchievingtheProvincialStandardinReading","ChangeinGrade3ReadingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinWriting","ChangeinGrade3WritingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematics","ChangeinGrade3MathematicsAchievementOverThreeYears"]].values, df.PercentageofGrade6StudentsAchievingtheProvincialStandardinMathematics)

- reg is just short for for  linear_model.LinearRegression()
- .fit will create the linear model
- df[ [Model variables] ].values DO NOT include answer in here
- If you do, the weight for that variable will be close to 100% as it is literally the answer
- After  df[ [Model variables] ].values, is df.Variable you are trying to predict  
( df.PercentageofGrade6StudentsAchievingtheProvincialStandardinMathematics )

### Line 136 
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L136  
print(reg.intercept_)
- reg.intercept_ will give you the b in the model that follows the format y = mx + b
- reg.coef_ will give a list of the m values as the program follows the format y = mx + b

## Predicting Values

### Line 160

print(reg.predict([ res[0:15] ]))  
- .predict will guess the value of what your .fit function was looking for
- inside the brackets will be a list of all the variables used to guess that variable 

### Line 164
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L164  

 print(reg.intercept_ + reg.coef_[0] * Enrolment_Input + reg.coef_[1] * Latitude_Input + LongitudeInput * reg.coef_[2] + PercentageofStudentsWhoseFirstLanguageIsNotEnglishInput * reg.coef_[3] + PercentageofStudentsWhoseFirstLanguageIsNotFrenchInput * reg.coef_[4] + PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountryInput * reg.coef_[5] + PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountryInput * reg.coef_[6] + PercentageofStudentsReceivingSpecialEducationServicesInput * reg.coef_[7] + PercentageofStudentsIdentifiedasGiftedInput * reg.coef_[8] +PercentageofGrade3StudentsAchievingtheProvincialStandardinReadingInput* reg.coef_[9] + ChangeinGrade3ReadingAchievementOverThreeYearsInput * reg.coef_[10] + PercentageofGrade3StudentsAchievingtheProvincialStandardinWritingInput * reg.coef_[11] + ChangeinGrade3WritingAchievementOverThreeYearsInput * reg.coef_[12] + PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematicsInput * reg.coef_[13] + ChangeinGrade3MathematicsAchievementOverThreeYearsInput * reg.coef_[14])

- This is a manual represntation of that the predict funtion does, it takes the variable, multiplies it by it weight and then adds up all resaults

### Line 173
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L173  

print(reg.score(df[['Enrolment',"Latitude","Longitude","PercentageofStudentsWhoseFirstLanguageIsNotEnglish","PercentageofStudentsWhoseFirstLanguageIsNotFrench","PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountry","PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountry","PercentageofStudentsReceivingSpecialEducationServices","PercentageofStudentsIdentifiedasGifted","PercentageofGrade3StudentsAchievingtheProvincialStandardinReading","ChangeinGrade3ReadingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinWriting","ChangeinGrade3WritingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematics","ChangeinGrade3MathematicsAchievementOverThreeYears"]].values , df.PercentageofGrade6StudentsAchievingtheProvincialStandardinMathematics  ))

- The .score function will use the prdict function on all 
- It is important to change df from your training.csv set df = pd.read_csv('https://raw.githubusercontent.com/0Domlightning0/MachineLearningOffical/main/OSSLT_Train.csv')   (https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L14)
- To your evaluation.csv set that the program has never seen before df = pd.read_csv("https://raw.githubusercontent.com/0Domlightning0/MachineLearningOffical/main/OSSLT_Eval.csv")




















