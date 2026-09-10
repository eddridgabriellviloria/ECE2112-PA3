# ECE 2112 PROGRAMMING ASSIGNMENT 3 - PYTHON DATA ANALYSIS (PANDAS)
## Programmed By: Eddrid Gabriell Viloria, 2ECE-C
This is the repository for the THIRD programming assignment for ECE 2112, Advanced Computer Programming and Algorithms. What you will see here is the .ipynb file of the assignment itself, alongside this README file.
##
**Objective/s:** The students/programmers' objectives are to be able to load a CSV file into the PANDAS dataframe. They are also tasked to be able to select rows and columns via positioning and label-based indexing, be able to filter records by using conditions on a dataframe column, and extract a well-defined subset data without changing the data of the source.


## Programming Problem A - Positional and Label-Based Slicing
* This programming problem is divided in 3 parts, each having a specific task:  
      - Display the shape and complete list of column of names of cars.  
      - Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.  
      - From cars_6_to_10, display only the columns model, mpg, cyl, hp, and gear, in that order.
* The first task was made by simply calling in the CSV file of the list itself (`cars.csv`). This can be done by using the command `pd.read_csv()`. Make sure the CSV file is in the same folder as the program itself:
```python
cars = pd.read_csv('cars.csv')
cars
```
* As an additional requirement, the programmer also used `cars.shape` in order to call in the shape of the dataframe.
```python
cars.shape
```
* The second item was done by using the command `.iloc[]` on the dataset that the programmer possesses, as noted in the requirements given in the instructions. Since the students must call in specifically row 6 to 10, the programmer must use a specific way to do so. This can be done by typing in the specific row numbers being asked in the square brackets. All the while, we equate this to cars_6_to_10, so that the program will recognize the dataset under this label.
```python
cars_6_to_10 = cars.iloc[[6, 7, 8, 9, 10]]
cars_6_to_10
```
* Finally, we were asked display specific information in each of the rows called in here. Apart from the model, this dataset should include the mpg, cyl, hp, and the gear in that order. This can be done via `.loc[,[]]`, to which the first part comprises the rows to be included in this data extraction, while the second part comprises of the specific information to be included in said rows. With all of this put together, we end up with this code.
```python
cars_6_to_10.loc[:, ['Model','mpg','cyl','hp','gear']]
```
## Programming Problem B - Model Lookup
* This programming problem contains two parts, with one for demonstration of the general idea of the function, while the other is for further understanding. The students are also required to use boolean indexing on the `model` column for this programming problem.  
        - Display the complete row for Toyota Corolla.  
        - For Pontiac Firebird, display only model, mpg, hp, and wt.
* As an additional requirement, the students were also tasked to store these results in `toyota` and `pontiac` as well, so we must equate the two results to each of these respectively as well.
* This code is used to display the complete row for Toyota Corolla. We simply don't specify any specific category of information, where python will assume to display everything present in the row:
```python
toyota = cars.loc[(cars['Model']=='Toyota Corolla')]
toyota
```
* As for the second item, to display the row of the Pontiac Firebird with only the model, mpg, hp, and wt, we simply use the same boolean indexing command, but this time the programmer must specify the exact columns present in the dataset. This is inserted after the comma after `(cars['Model']=='Toyota Corolla')`. Doing so will let us form this code:
```python
pontiac = cars.loc[(cars['Model']=='Pontiac Firebird'),['Model','mpg','hp','wt']]
pontiac
```
## Programming Problem C - Multi-Model Subsetting
* On this last programming problem, the students are tasked to create a dataframe named `selected_cars`, which will only record three models, alongside their mpg, cyl, hp, and gear: Datus 710, Lotus Europa, and Ferrari Dino.
* The programmers must select these rows strictly by their models. They can do this using logic operators, specifically "or", which is denoted as `|`. We can use this in the same code format we used from the second programming problem in order to include more than one model. However, we must use the code `(cars['Model']=='')` multiple times inside the square bracket in order to call in all three desired models. The specific columns to include are not required to be typed in multiple times for each call of these specific car models. Combining all of this, we end up with this code:
```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710')|(cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'),['Model','mpg','cyl','hp','gear']]
selected_cars
```
* As an additional requirement, the programmer also used `cars.shape` in order to call in the shape of the dataframe.
```python
selected_cars.shape
```
## Versions
**Sept. 04, 2026**  
* Version 0.1 (Date of commit listed as September 09, 2026)  
    - Development of PA3 initiated.
    - Solutions for Programming Problems A and B are fully functional.
 
**Sept. 10, 2026**
* Version 1.0
    - Solution for Programming Problem C fully functional.
* Version 1.1
    - Commands for calling in the shape of `cars` and `selected_cars` added.
