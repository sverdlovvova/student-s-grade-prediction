# student-s-grade-prediction
Predicting a student's grade based on social information about him

The dataset contains the following information about 395 students:

1. school - student's school (binary: 'GP' - Gabriel Pereira or 'MS' - Mousinho da Silveira)

2. sex - student's sex (binary: 'F' - female or 'M' - male)

3. age - student's age (numeric: from 15 to 22)

4. address - student's home address type (binary: 'U' - urban or 'R' - rural)

5. famsize - family size (binary: 'LE3' - less or equal to 3 or 'GT3' - greater than 3)

6. Pstatus - parent's cohabitation status (binary: 'T' - living together or 'A' - apart)

7. Medu - mother's education (numeric: 0 - none, 1 - primary education (4th grade), 2 – 5th to 9th grade, 3 – secondary education or 4 – higher education)

8. Fedu - father's education (numeric: 0 - none, 1 - primary education (4th grade), 2 – 5th to 9th grade, 3 – secondary education or 4 – higher education)

9. Mjob - mother's job (nominal: 'teacher', 'health' care related, civil 'services' (e.g. administrative or police), 'at_home' or 'other')

10. Fjob - father's job (nominal: 'teacher', 'health' care related, civil 'services' (e.g. administrative or police), 'at_home' or 'other')

11. reason - reason to choose this school (nominal: close to 'home', school 'reputation', 'course' preference or 'other')

12. guardian - student's guardian (nominal: 'mother', 'father' or 'other')

13. traveltime - home to school travel time (numeric: 1 - 1 hour)

14. studytime - weekly study time (numeric: 1 - 10 hours)

15. failures - number of past class failures (numeric: n if 1<=n<3, else 4)

16. schoolsup - extra educational support (binary: yes or no)

17. famsup - family educational support (binary: yes or no)

18. paid - extra paid classes within the course subject (Math or Portuguese) (binary: yes or no)

19. activities - extra-curricular activities (binary: yes or no)

20. nursery - attended nursery school (binary: yes or no)

21. higher - wants to take higher education (binary: yes or no)

22. internet - Internet access at home (binary: yes or no)

23. romantic - with a romantic relationship (binary: yes or no)

24. famrel - quality of family relationships (numeric: from 1 - very bad to 5 - excellent)

25. freetime - free time after school (numeric: from 1 - very low to 5 - very high)

26. goout - going out with friends (numeric: from 1 - very low to 5 - very high)

27. Dalc - workday alcohol consumption (numeric: from 1 - very low to 5 - very high)

28. Walc - weekend alcohol consumption (numeric: from 1 - very low to 5 - very high)

29. health - current health status (numeric: from 1 - very bad to 5 - very good)

30. absences - number of school absences (numeric: from 0 to 93)

Using the df.isna (). Sum () method, I made sure that the dataset does not contain null values.

Then I started working with the object type traits. By plotting the histograms, I saw that:

1. Most students attend GP school.

2. There are slightly more female students than male students.

3. Most of the students live in the city.

4. Most students have more than 3 people in their families.

5. The parents of most students live together.

6. The parents of most students work in the service sector.

7. Most of the students listed their mother as their guardian.

8. Most students do not study anywhere other than school.

9. Most students do not take extra classes.

10. Most of the students attended kindergarten.

11. Most of the students are going to get higher education.

12. Most students have access to the Internet at home.

13. Most students have no relationship.

For convenient work with data represented by the object type, let's convert them to an integer type using LabelEncoder.

Let's change the dataset a bit. Remove the students whose final grade is 0. 357 students remain. Let's merge the Dalc and Walc columns as well, because they contain similar information.

Let's build a correlation map. We will see that the final score does not depend on failures. Then we will not use this feature in the construction of the model.

Let's split the data into train and test with test_size = 1/3 and train the model using LinearRegression, DecisionTreeRegressor and RandomForestRegressor.

LinearRegression: RMSE=3.199, MAE=2.513

DecisionTreeRegressor: RMSE=3.561, MAE=2.933

RandomForestRegressor: RMSE=2.961, MAE=2.371
