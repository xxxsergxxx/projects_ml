Numpy:

#Tasklist:

1.  Find the target in the dataset and remove this column from the dataset (delete by index)

2.  Convert the remaining columns to a 2D array (or make sure that it is already a 2D array)

3.  Calculate mean, median, standard deviation for the 1st column

4.  Insert 20 values of np.nan at random positions in the array (using normal randomization, there may be overlapping positions, so find a solution that guarantees 20 unique positions)

5.  Find the positions of the inserted np.nan values in the 1st column

6.  Filter the array by the condition: values in the 3rd column > 1.5 and values in the 1st column < 5.0 (save to another variable)

7.  Replace all np.nan values with 0

8.  Count all unique values in the array and print them along with the number

9.  Split the array vertically into 2 equal parts (do not use absolute numbers, there should be two arrays of 4 columns each)

10.  Sort both arrays by the 1st column: 1st in ascending order, 2nd in descending order

11.  Merge both arrays into one

12.  Find the most frequently repeated value in the array

13.  Write a function that multiplies all values in a column that are less than the average value in that column by 2 and divides the remaining values by 4.

14.  Apply the resulting function to the 3rd column