# Laplace-equation

## Using the Laplace equation, I am approximating the unknown values in a matrix with known boundaries. This is done by finding an average of all the points around that unknown value. This is done in both 2D and 3D space.

Parameters

U = The matrix including all the boundary values as well and the locations of the % unknowns that we are trying to approximate

Finding the solution:

1. Error checking and warmings are done to see if the input is a 2D array for Laplace2D or a 3D array for Laplace3D. If it is a higher or lower order array, it will output an error and a warning message. 
2. Initilize a 2D(or 3D) matrix given the size of the input array that can be used to map in the next step.
3. I am mapping each of the "m" unsolved points to a unique number from 1 to m. This will allow the user to know where the unknowns are as well as the numbers around them that need to be solved. 
4. Using the information from step 3, I am creating an appropriately sized matrix of zeros and a vector of zeros. To update the matrix and the vector, I am checking the adjacent points to the i th unknown point. If it is an insulated boundary, nothing happens. If it is a Dirichlet boundary conditions, 1 is subtracted from the i  th diagonal entry of the matrix and subtract the value from the i th entry of the vector. If there is another unknwon at the position j, subtract 1 from the ith diagonal entry of the matrix and add 1 to the (i, j)th entry of the matrix. 
5. Solving for U_out by dividing the vector **b** by the matrix **M**.

**Exmaple: Solving for the unknown points given these boundaries**

![image](https://user-images.githubusercontent.com/58648072/130154459-15f44818-60ab-43fe-8d94-4680a3f45b4d.png)

![image](https://user-images.githubusercontent.com/58648072/130154527-5877ff70-0847-4ee0-b2da-3cf1a4e503dd.png)

![image](https://user-images.githubusercontent.com/58648072/130154551-77afcf58-5878-440d-aa6e-bfd3e3f8820f.png)

**Example: Solving for the unknown points where one wall is at 100&deg;C, two adjacent walls are at 0&deg;C and the found wall opposite the hot wall and the ceiling and floor are insulated.**

![image](https://user-images.githubusercontent.com/58648072/130154745-3e6ea260-7702-4f5c-9a72-ee02acd2bf91.png)

**Example: Solving for the interior points given a cross section of a rectangular cable with two wires on the inside**

![image](https://user-images.githubusercontent.com/58648072/130154844-ca6028e6-8772-475e-ae36-3aec0d3ac1b8.png)

A plot of an approximation of the voltage potentials of the cable

![image](https://user-images.githubusercontent.com/58648072/130154873-67253b55-29c4-4b85-ae64-7fe9cc8789a1.png)
