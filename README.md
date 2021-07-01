# Donor-Choose-Appliction-Screening
The goal of the project is to predict whether or not a DonorsChoose.org project proposal submitted by a teacher will be approved, using the text of project descriptions as well as additional metadata about the project, teacher, and school. DonorsChoose.org can then use this information to identify projects most likely to need further review before approval.
Data Insights

Number of data points and features **(109248, 17)
**
**Distribution of classes**

**85 percent of projects are approved and 15 percent of projects are not approved.**

Features

We have in total 17 features: project_id, project_title, project_grade_category,project_subject_catgories,school state, project_subject_subcategories,project_resource_summary,project_essay_1,2,3,4,project_submitted datetime,teacher_id,teacher_prefix,teacher_number_of_previously_posted_projects,description,quantity and price.

**School State:** This feature is a categorical feature which contains the list of the state of the school from which they have received the proposal.

After analysing we observe that the percentage of approval varies from state to state but not that much. The state with least number of proposal acceptance is 80 percent whereas state with maximum number of proposal acceptance is 90 percent

**Teacher Prefix:** This feature again is a categorical feature. It has categories such as Mrs.,Mr.,Dr,Ms.,Teacher.
From EDA we observe that teachers with prefix Mrs. has maximum number of project proposals and teachers with prefix Dr. have the least number of proposals.

In acceptance teachers with prefix Mrs. and Ms. have maximum approval rate. Whereas teacher with prefix Dr. and Teacher have the least approval rate.

**Project Grade Category:** 

![image](https://user-images.githubusercontent.com/61081294/124124898-9e41e400-da96-11eb-9c59-164885abf31f.png)


From above data we observe that Grades PreK-2 has maximum number of submissions whereas Grades 9-12 has least. Also we observe that 

**Project_subject_categories:**


![image](https://user-images.githubusercontent.com/61081294/124125035-c92c3800-da96-11eb-9df6-2e82232ed4af.png)



Before analysing the above categories we firstly preprocess the categories by removing the spaces, ‘&’ and ‘The’ word. Also we have replaced & with ‘_’ .After preprocessing now we analyse it.


![image](https://user-images.githubusercontent.com/61081294/124125439-3b9d1800-da97-11eb-94d2-eb3810195137.png)


Here we observe that percentage approval varies amongst categories. But percentage of submission is hughes in literacy_langauge category

Project_subject_subcategories:

We first preprocess the subcategories and analyse it afterwards.


![image](https://user-images.githubusercontent.com/61081294/124125690-8c147580-da97-11eb-94e2-d930c70338d5.png)


After analysing project_subject_subcategory feature we get the below results:

(https://user-images.githubusercontent.com/61081294/124126156-01804600-da98-11eb-87b4-d8fc2771b770.png)


We observe that the project approval percentage varies amongst the categories. Literacy subcategory has the highest percentage of approval which is 88 percent and varies amongst the categories.

**Text features (Title):**

**Analyzing text feature:**

Step 1: We first obtain the sentences with their respective counts of words.
Step 2: We then observe how the approval rate is affected by increase or decrease in the number of words.With the help of Box Plot and kde plot.

Observation: We observe that the approved projects have more words in their project title.

**Text features (Essay):**

Same observation we have with essays. We observe that essays with more words tend to have a high approval rate.

**Cost per project:**

Though we were not able to extract much information from bar and kde plots thus we resort to percentile values. In explanation, we obtained cost of approved and disapproved projects upto a certain percentile and we observed that the projects with higher cost tend to get rejected.

**Previously Posted Projects:**

We plotted the data of previously posted projects but it didn’t help us much in classification because there isn't much difference in numbers of approved and rejected projects.

**Project Resource Summary:**

This includes the list of the resources required for the project. Through box-plot,kde plot and percentile values we observe that Project Resource Summary doesn’t add much value in our classification.

**Preprocessing and Predictive Modelling:**

We are using 100k data points for predictive modelling and we consider 9 features for predictive modelling. 

**Train data points: 64,000 in total
Cross Validation data points: 16000
Test data points: 20000**


We encode our features using OneHotEncoding and tfidf.

**Peformance Metric:** Performance Metric used are Confusion Metric to track how our model is performing against false positive and false negative scenerios also we are using ROC-AUC score to be used as metric which returns a single value that gives the performance of the metric.

Models used in Predictive Modelling are **KNN,Naive Bayes, Logistic regression and Random Forest.**
And it was observed that Logistic Regression outperforms every other algorithm.
