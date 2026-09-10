# ECE 2112 PROGRAMMING ASSIGNMENT 3 - PYTHON DATA ANALYSIS (PANDAS)
## Programmed By: Eddrid Gabriell Viloria, 2ECE-C
This is the repository for the THIRD programming assignment for ECE 2112, Advanced Computer Programming and Algorithms. What you will see here is the .ipynb file of the assignment itself, alongside this README file.
##
**Objective/s:** The students/programmers' objectives are to be able to load a CSV file into the PANDAS dataframe. They are also tasked to be able to select rows and columns via positioning and label-based indexing, be able to filter records by using conditions on a dataframe column, and extract a well-defined subset data without changing the data of the source.


## Programming Problem A - Positional and Label-Based Slicing
* The programmer was tasked to create a normalized array by using the formula `Z = (X - ¯x)/σ` on a 5x5 integer ndarray named X.
* The programmer was also tasked to make the array with this code:
```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
* In order to implement the given formula to the array, and equate it under the name X_Normalized, I used this code in order to do so.
```python
X_Normalized = (X-X.mean())/(X.std())
X_Normalized
```
* Afterward, we were then tasked to display the array X, alongside the normalized mean and standard deviation, using via using these codes:
```python
X
X_Normalized.mean()
X_Normalized.std()
```
* Finally, we were asked to save the normalized array as a `.npy` file. In order to do so, I used this code for the program to save the normalized array as a `.npy` file.
```python
np.save("X_normalized",X_Normalized)
```
## Programming Problem B - Model Lookup
* First, we were tasked to create a 10 x 10 array containing the first 100 positive integers. This can be done by inputting this code into Python, followed by the variable itself, in order for the array to print:
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
