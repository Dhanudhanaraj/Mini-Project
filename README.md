# Mini-Project

# ANALYSIS OF STUDENT MENTAL HEALTH

## AIM:

To Perform Analysis of student mental health on the given dataset by using EDA.

## Explanation

### What is DataScience?

1.Data science is a multidisciplinary field that combines techniques, tools, and methodologies to extract knowledge and insights from structured and unstructured data. 

2.It involves applying scientific methods, statistical analysis, machine learning algorithms, and data visualization techniques to understand and solve complex problems and make data-driven decisions.

### Steps in Datascience?
![image](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/11446101-4f20-47d0-a084-b9ca084e6669)

### Uses in Datascience?
![image](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/8a52cf4b-7535-4f72-a215-585b5d95cb19)

## Program:
```
DHANUMALYA D-212222230030
KOWSALYA M-212222230069
SUJITHRA B K N-212222230153

# CODE:
# IMPORTING LIBRARIES
import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)
import seaborn as sns 
import matplotlib.pyplot as plt
import missingno as msno
import plotly.graph_objs as go
import plotly.express as px
plt.style.use('seaborn-dark')
plt.style.context('grayscale')
%matplotlib inline
from wordcloud import WordCloud, STOPWORDS

# LOADING DATASET
df=pd.read_csv("/content/Student Mental health.csv")
df

df.head()

# EXPLORATORY SOME INFORMATION ABOUT DATASET
df.isnull().sum()

df.Age.mean()

df.Age.fillna("21",inplace=True)

df.Age.isnull().sum()

df.isnull().sum()

df.info()

df.shape

df.rename(columns = {'Choose your gender':'gender',
                     'What is your course?':'course', 
                     'Your current year of Study':'year_of_Study',
                     'What is your CGPA?':'CGPA', 
                     'Marital status':'Marital_status', 
                     'Do you have Depression?':'Depression', 
                     'Do you have Anxiety?':'Anxiety',
                     'Do you have Panic attack?':'Panic_attack', 
                     'Did you seek any specialist for a treatment?':'treatment'}, inplace = True)

df.head()

df['Date'] = pd.to_datetime(df['Timestamp'], errors='coerce')
df['day'] = (df['Date']).dt.day
df['month'] = (df['Date']).dt.month
df['year'] = (df['Date']).dt.year
df['hour'] = (df['Date']).dt.hour

df.head()

# DATA VISUALIZATION
df.year.value_counts()

df.day.value_counts()

fig = px.histogram(df, x="day", color="day")
fig.show()

df.month.value_counts()

fig = px.histogram(df, x="month", color="month")
fig.show()

df.hour.value_counts()

fig = px.histogram(df, x="hour", color="hour")
fig.show()

df.gender.value_counts()

fig = px.histogram(df, x="gender", color="gender")
fig.show()

df.Age.value_counts()

fig = px.histogram(df, x="Age", color="Age")
fig.show()

df.course.value_counts()

fig = px.histogram(df, x="course", color="course")
fig.show()

df.loc[(df['year_of_Study'] =="Year 3"), 'year_of_Study'] = 'year 3'
df.loc[(df['year_of_Study'] =="Year 2"), 'year_of_Study'] = 'year 2'
df.loc[(df['year_of_Study'] =="Year 1"), 'year_of_Study'] = 'year 1'

df.year_of_Study.value_counts()

fig = px.histogram(df, x="year_of_Study", color="year_of_Study")
fig.show()

df.CGPA.value_counts()

fig = px.histogram(df, x="CGPA", color="CGPA")
fig.show()

df.Marital_status.value_counts()

fig = px.histogram(df, x="Marital_status", color="Marital_status")
fig.show()

df.Depression.value_counts()

fig = px.histogram(df, x="Depression", color="Depression")
fig.show()

df.Anxiety.value_counts()

fig = px.histogram(df, x="Anxiety", color="Anxiety")
fig.show()

df.Panic_attack.value_counts()

fig = px.histogram(df, x="Panic_attack", color="Panic_attack")
fig.show()

df.treatment.value_counts()

fig = px.histogram(df, x="treatment", color="treatment")
fig.show()

fig = px.histogram(df, x="Depression",color='treatment', barmode='group',height=400)
fig.show()

fig = px.histogram(df, x="Anxiety",color='treatment', barmode='group',height=400)
fig.show()

fig = px.histogram(df, x="Anxiety",color='treatment', barmode='group',height=400)
fig.show()

fig = px.box(df, x="gender", y="Age",color="gender", notched=True,title="Box plot of Gender",)
fig.show()

fig = px.box(df, x="Marital_status", y="Age",color="Marital_status", notched=True, title="Box plot of status")
fig.show()

fig = px.box(df, x="year_of_Study", y="Age",color="year_of_Study", notched=True, title="Box plot of study",)
fig.show()
```
## OUTPUT :
![m1](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/6718fc03-e365-4e6b-864f-cc330d26fcaf)
![m2](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/58a3a742-698e-445f-b229-a59a8dfef6ff)

![m3](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/f160067c-1519-4349-8401-e50c8b4e7bcf)
![m4](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/c7ed2ac6-7e66-407a-951f-08a96d63ef51)
![m6](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/4ddd1e30-9d03-4427-a2d3-d9af8172524b)
![m7](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/a9bae15c-e59c-42c0-a85d-c5da19daf139)
![m8](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/ff6b195d-8a0a-4f31-af24-1b8cc1102141)
![m9](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/d237e233-bef6-4253-8801-274e4479cb2b)
![m10](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/ae1fda6d-f752-40f9-a4c3-e39fda1daab6)
![m11](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/cbbae2f7-6c7e-4f47-99f5-579e11ca52e1)
![m12](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/6232c615-a10a-425e-9a0a-435cf3ce5910)
![m13](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/b9a963e0-fa2b-4e09-8d7b-9564f08d55f3)
![m14](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/26e1a9e5-bd41-4fee-a11a-6fde6aa1962f)
![m15](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/cb503d58-f77a-4703-bac4-cf31249bf511)
![m16](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/4e4c64f1-ee66-45eb-a3d3-23463194c5ee)
![m17](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/5d679683-93fe-45f2-81bc-3bd972d725e3)
![m18](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/1b8abed9-e71f-470c-95d7-8c32f2badde1)
![m19](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/1bb83ae8-8f92-448f-a3d6-78f77e751421)
![m20](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/142450f4-ab98-4e91-864d-202e73cbce98)
![m21](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/d4daa799-5bfa-4f63-a171-b769e0a0995c)
![m22](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/89aabbf0-69fb-485d-b230-023727c8edf2)
![m23](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/9aa87343-0b35-4ea2-b589-6e3685b38b0d)
![m24](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/c897efce-9f97-4dcd-a6b8-9b2f04b816d4)
![m25](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/cfbd7e35-2c15-49d0-87de-6f3013ef5bf1)
![m26](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/01da2a62-0511-4569-ae22-9da3f2fe08ea)
![m27](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/32b197e0-dcae-4d5b-8e72-ce22a9ac4b4c)
![m28](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/75150e25-99d5-4771-b741-1e345d9ac47d)
![m29](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/586918fc-3d99-4b25-ba2b-4b0d196f9e8d)
![m30](https://github.com/Dhanudhanaraj/Mini-Project/assets/119218812/10c86e7d-bdb0-4eca-9890-b845ecc9f3a0)

## CONCLUSION :
1.This survey was usually done on the 7th.
2.This survey was started at the 8th month and continued at the 9th and 10th months.
3.This survey was usually done at noon.
4.The survey was mostly answered by women.
5.Respondents are usually 18-year-olds, presumably in their first year at university.
6.Participants usually consist of people from the 4-year department.
7.Respondents to the questionnaire generally consist of first-year students.
8.The average of respondents to the survey is between 3.5 and 4.
9.Marital status is generally single.
10.They are not usually depressed.
11.They usually do not have anxiety problems.
12.They usually do not experience panic attacks.
13.They often do not receive expert support.
14.Some of those who are depressed receive professional support.
15.Some of those experiencing anxiety receive professional support. When this percentage is multiplied, it is higher than for those who show symptoms of depression.
16.Some of those experiencing panic attacks receive professional support. This rate is higher than others.
17.The average age of men is higher than that of women. However, the number of women in this dataset was high. Then we can say that the age of the men who answered this questionnaire is more than the age of the women. For example, if the age of women responding is around 18, the average age of men varies between 18-24.
18.Since the age of marriage is 18 and over in the law, the average age of married people is 21.
19.While the average age of the 1st and 2nd year students is close to each other, the average age increases as the grade level increases.

## RESULT :
Thus, Data analysis is performed on the given dataset and save the data to a file.
