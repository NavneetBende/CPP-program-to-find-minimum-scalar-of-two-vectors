Finding the minimum scalar product in C++
Here, in this page we will discuss the program to find the minimum scalar product in C++ programming language. We are given with two arrays and need to print the value of minimum scalar product that obtained.

Find minimum scalar product in Cpp
While loop in C
Method Discussed :
Method 1 : Without using inbuilt sort() function for sorting.
Method 2 : Using sort() function for sorting.
Let’s discuss both methods one by one in brief,

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
Minimum scalar product in C++
Related Pages
Finding Non Repeating elements in an Array

Removing Duplicate elements from an array

Finding Maximum scalar product of two vectors in an array 

Counting the number of even and odd elements in an array 

Find all Symmetric pairs in an array 

Method 1 : Code in C++
Run
#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr1[] = {1, 2, 6, 3, 7};
   int arr2[] = {10, 7, 45, 3, 7};

   int n = sizeof(arr1)/sizeof(arr1[0]);


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

    cout<< product;

}
Output
149
Method 2 :
In this method we will use inbuilt sort function to sort the array.

For, sorting arr1 in ascending order, use sort(arr1, arr1+n)
For, sorting arr2 in descending order, use sort(arr2, arr2+n, greater()).
Time and Space Complexity :
Time Complexity : O(n log(n))
Space Complexity : O(1)
How to sort in descending order?
sort() takes a third parameter that is used to specify the order in which elements are to be sorted.
We can pass the “greater()” function to sort in descending order.
This function does a comparison in a way that puts greater elements before.
Method 2 : Code in C++
Run

#include<bits/stdc++.h>
using namespace std;

int main(){

   int arr1[] = {1, 2, 6, 3, 7};
   int arr2[] = {10, 7, 45, 3, 7};

   int n = sizeof(arr1)/sizeof(arr1[0]);


   //Sort arr1 in ascending order
   sort(arr1, arr1+n);
//Sort arr2 in descending order
sort(arr2, arr2+n, greater<int>()); int product = 0; 
for(int i=0; i<n; i++) product += arr1[i]*arr2[i]; 
cout<< product; 
}
Output
149
