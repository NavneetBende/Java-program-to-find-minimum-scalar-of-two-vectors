Minimum scalar product of two vectors
In this section we will discuss the program to find the minimum scalar product of two vectors using java. We are given with two integer arrays and need to find the minimum scalar product obtained.

Minimum scalar product of two vectors
Example
Input :arr1[4] = [10, 30, 40, 20]
            arr2[4] = [2, 4, 5, 1]
Output : 230
Explanation : 10*5 + 20*4 + 30*2 + 40*1 = 230
Here, we will discuss the two different ways for solving the problem. These two different ways are :

Method 1 : Sorting Without using inbuilt function.
Method 2 : Sorting using inbuilt sort function.
Method 1 :
Sort the first array in ascending order,
Sort the second array in descending order.
Declare a variable say product = 0.
Run a loop from index 0 to n
Set product += (arrr1[i]*arr2[i])
After complete iteration print product.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Minimum Scalar product in java
Related Pages
Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Finding Maximum scalar product of two vectors in an array 

Counting the number of even and odd elements in an array 

Find all Symmetric pairs in an array 

Method 1 : Code in Java
Run
class Main
{
    public static void main (String[] args)
    {
           int arr1[] = {1, 2, 6, 3, 7};
           int arr2[] = {10, 7, 45, 3, 7};
           int n = arr1.length;

           //Sort arr1 in ascending order
           for(int i=0; i<n; i++){
                for(int j=i+1; j<n; j++){ if(arr1[i]>arr1[j]){
                       int temp = arr1[i];
                       arr1[i] = arr1[j];
                       arr1[j] = temp;
                    }
                }
            }

           //Sort arr2 in descending order
           for(int i=0; i<n; i++){
                for(int j=i+1; j<n; j++){
                    if(arr2[i]<arr2[j]){
                        int temp = arr2[i];
                        arr2[i] = arr2[j];
                        arr2[j] = temp;
                    }
                 }
            }

          int product = 0;
          for(int i=0; i<n; i++)
              product += arr1[i]*arr2[i];

          System.out.print(product);
   }
}
Output
149
Method 2 :
In this method we will use inbuilt sort function to sort the array.

For, sorting arr1 in ascending order, use Arrays.sort(arr1)
For, sorting arr2 in descending order, use Arrays.sort(arr2, Collections.reverseOrder());.
Time and Space Complexity :
Time Complexity : O(n log(n))
Space Complexity : O(1)
Method 2 : Code in Java
Run
import java.util.Arrays;
import java.util.Collections;
class Main
{
    public static void main (String[] args)
    {
          Integer arr1[] = {1, 2, 6, 3, 7};
          Integer arr2[] = {10, 7, 45, 3, 7};
          int n = arr1.length;

          //Sort arr1 in ascending order
          Arrays.sort(arr1);

          //Sort arr2 in descending order
          Arrays.sort(arr2, Collections.reverseOrder());

          int product = 0;
          for(int i=0; i<n; i++)
              product += arr1[i]*arr2[i];

          System.out.print(product);
   }
}
Output
149
