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
* This programming problem contains two parts, with one for demonstration of the general idea of the function, while the other for further understanding.  
        - Display the complete row for Toyota Corolla.  
        - For Pontiac Firebird, display only Model, mpg, hp, and wt.  
```python
A = np.arange(1,101,1)
A
```
* After this, we are then tasked to cube every element in the array, which will be under a new name called `C`. This can be done by inputting this code after the former.
```python
C = A.reshape(10,10)
C = C*C*C
C
```
* Lastly, we were tasked to create a Boolean condition on array C to obtain all the cubed elements that are divisible by 4. This new array would be labeled as `div_by_4`, and will be saved as a `.npy` file. We will be using this code in order to achieve its goal:
```python
div_by_4 = C[C%4==0]
div_by_4
```
* This will then be followed by this code in a separate cell:
```python
np.save("div_by_4",div_by_4)
```
## Programming Problem C - Multi-Model Subsetting
* We were tasked to create a 6 x 6 array, labeled as `S`, containing the squares of the first 36 positive integers in increasing row-major order. This can be done by inputting this series of code into Python:
```python
S = np.arange(1,37,1)
S = S.reshape(6,6)
S = S*S
S
```
* Next, we were then tasked to compute the mean of all elements of S, labeled as `S_mean`. This can be done via this code here:
```python
S_mean = S.mean()
S_mean
```
* Lastly, we are tasked to filter out the array, making it so that it will only select elements strictly greater than the computed mean, `S_mean` in this case. This can be done with Boolean conditions. This new array will thus be named and saved into a `.npy` file as `above_mean`, all done with this code:
```python
above_mean = S[S>S_mean]
above_mean

np.save("above_mean",above_mean) #This is written on a separate cell
```
## Versions
**Aug. 27, 2026**  
* Version 0.1 (Not listed in GitHub commits unfortunately)  
    - Development of PA2 initiated.
 
**Aug. 30, 2026**  
* Version 0.2 (Not listed in GitHub commits unfortunately)  
    - Programming Problem A development finished.
* Version 0.3 (Not listed in GitHub commits unfortunately)  
    - Programming Problem B development finished.
* Version 1.0
    - Programming Problem C development finished.
    - Entire project fully published on GitHub

**Aug. 27, 2026**
* Version 1.1
    - Hotfix on the missing 'np.save()' for `above_mean` on Programming Problem C
