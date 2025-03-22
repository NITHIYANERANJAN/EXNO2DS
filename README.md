# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![361677677-7e5e17a3-0ca7-465f-b728-d3c67a2a4f7d](https://github.com/user-attachments/assets/988efb87-c540-48fd-a6d0-fe33f5e57b75)
## df.info()

![361677153-d603f787-94f1-4138-819d-418a86f5ddea](https://github.com/user-attachments/assets/e1f49bca-e714-417b-ae4a-7b2ce3709324)
## df.shape
![361677766-4e2ffc5f-d198-4f87-bf17-e75162558d79](https://github.com/user-attachments/assets/97d9098e-8c3c-4f7b-b8ef-fe4400699aaa)
## df.describe()
![361677915-bc6d662d-2259-4ca7-b3bf-a0c3e612cd4b](https://github.com/user-attachments/assets/1307157c-e110-4aea-a95a-fa4ca9f148f7)

## df.set_index("PassengerId",inplace=True)
## df.describe()
![361679106-f1cb5106-e322-4800-a8ca-87f242eeb6ac](https://github.com/user-attachments/assets/07936145-b19b-4821-ad42-5606a461f776)
## df.nunique()
![361679375-16756e99-833c-412a-ba62-39defb8408b6](https://github.com/user-attachments/assets/9e50613d-0c97-4831-aa9d-21cad20d5176)
## df["Survived"].value_counts()
![362538980-f8cd1730-ac50-4e4b-8299-df5e2d4cbc84](https://github.com/user-attachments/assets/710015ce-7fb3-444c-8559-fdd48203ee3e)

## per=(df["Survived"].value_

![361680002-ca17452e-4508-4d6e-a724-a4c79a8a4152](https://github.com/user-attachments/assets/002bd98c-11d4-40cb-b4c6-395467601517)
counts()/df.shape[0]*100).round(2)
## sns.countplot(data=df,x="Survived")
![361680213-6edb9293-3408-432a-aff6-29073117693b](https://github.com/user-attachments/assets/af255087-2259-43c4-9b33-9dfb90dcaf38)
## df.Pclass.unique()
![361680424-b5fae832-3ca6-4bc9-9b38-c25ba29f4503](https://github.com/user-attachments/assets/f173fde1-71ae-4faa-8cb5-d66e505df39b)
## df.rename(columns= {'Sex':'Gender'}, inplace=True)
![361680672-45c69834-ef85-4b91-9a98-af73278edd81](https://github.com/user-attachments/assets/66fa890b-add4-4f7e-80fb-ca9525800c52)
## sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![361681291-1f4e823f-312e-4a23-baa4-4372015fe9da](https://github.com/user-attachments/assets/3c673d38-27cc-4c1e-aeaa-990edfc54335)
## sns.catplot(x='Survived',hue="Gender",data=df,kind="count")

![361681492-d5c1e2c6-7932-40a9-8ed6-36b86738b0bd](https://github.com/user-attachments/assets/7fd601b0-5dc5-43af-9c8e-bd901a15bbc8)
 ## df.boxplot(column="Age",by="Survived")
 ![361681628-9ef48650-fc8d-4d2b-9705-6fd2c5dac1f7](https://github.com/user-attachments/assets/c0da1927-6181-4b81-9a33-32ddb3ad4ffa)
## sns.scatterplot(x=df["Age"],y=df["Fare"])
![361681792-7a11bb7d-5ee8-402a-92c6-0753d8e5ac27](https://github.com/user-attachments/assets/d66d2beb-f9a5-4bf0-80b0-90c5c56c3bb7)

## sns.jointplot(x="Age",y="Fare",data=df)
![361682057-a280a685-5f5d-4842-b53b-62042d0df77b](https://github.com/user-attachments/assets/7ad0241e-12ef-4306-baae-e0e582cdff2b)
 ## fig,ax1 = plt.subplots(figsize=(8,5))
 pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
 ![361682306-b1f4d0ae-9300-427a-8f7f-753d61661708](https://github.com/user-attachments/assets/b45ce949-6ad2-4458-8967-83b6a2877359)
## sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="Count")
![362540761-dc5ae73b-a7a5-45a2-a1dc-7e4f0f0bfb52](https://github.com/user-attachments/assets/ac1b5d57-2d66-451a-8134-9d041d46a26b)
## corr = df.corr()

sns.heatmap(corr,annot=True)

![362541150-1444abfb-ca59-4081-9842-698369d1670b](https://github.com/user-attachments/assets/fab28ab5-3ed8-4359-8bf6-6e382a183caf)

## sns.pairplot(df)
![361682568-8478ee30-f907-483b-8772-2693e57ada6e](https://github.com/user-attachments/assets/e94d0676-7750-4796-940d-84bd9cba670d)

# RESULT
Hence performing Exploratory Data Analysis on the given data set is successfully.
