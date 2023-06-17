### Code for SKL
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py

### Project 
https://github.com/0Domlightning0/MachineLearningOffical

### Useful programs to gain understanding again
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/TestingTheTensorWebsite.py  
- Free example on the tensorflow website 

## Key pieces 

### Line18
https://github.com/0Domlightning0/MachineLearningOffical/blob/main/CompleteScuffed.py#L18  
list_of_variables = ['Enrolment',"Latitude","Longitude","PercentageofStudentsWhoseFirstLanguageIsNotEnglish","PercentageofStudentsWhoseFirstLanguageIsNotFrench","PercentageofStudentsWhoAreNewtoCanadafromaNonEnglishSpeakingCountry","PercentageofStudentsWhoAreNewtoCanadafromaNonFrenchSpeakingCountry","PercentageofStudentsReceivingSpecialEducationServices","PercentageofStudentsIdentifiedasGifted","PercentageofGrade3StudentsAchievingtheProvincialStandardinReading","ChangeinGrade3ReadingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinWriting","ChangeinGrade3WritingAchievementOverThreeYears","PercentageofGrade3StudentsAchievingtheProvincialStandardinMathematics","ChangeinGrade3MathematicsAchievementOverThreeYears"]

- This is a list of all your variables, very useful for copy and pasting into code 
- Also used for indexing

## Getting rid of empty data

- Empty data in machine learning will most likely crash the proram 

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


















