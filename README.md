# Given-a-list-arr-of-N-integers-print-sums-of-all-subsets-in-it-in-C

Sums of all Subsets in C
Here, in this page we will discuss the program for printing the sums of all subsets in C programming language. We are given with a list array of N integers, and need to print the all subsets sums.

Sums of all Subsets in C
While loop in C
Method Discussed :
Method 1 : Iterative Method
Method 2 : Recursive Method
 
Method 1 :
The total number of subset will be 2n, where n is the size of the array.
Run a loop from  0 to 2n -1.
Now, Pick all array elements which correspond to 1s in binary representation of ith number.
Method 1 : Code in C
Run
#include <stdio.h>

void subsetSums(int arr[], int n)
{
    // There are total 2^n subsets
    long long total = 1 << n;
 
    // Consider all numbers from 0 to 2^n - 1
    for (long long i = 0; i < total; i++) {
        long long sum = 0;
        for (int j = 0; j < n; j++)
            if (i & (1 << j))
                sum += arr[j];
 
        // Print sum of picked elements.
        printf("%lld ", sum);
    }
}
 
int main()
{
    int arr[] = { 4, 3, 5 };
    int n = sizeof(arr) / sizeof(arr[0]);
 
    subsetSums(arr, n);
    return 0;
}
Output
0 4 3 7 5 9 8 12
Related Pages
Program to check Prime Number

Program to print Prime Number in range

Program to reverse a number

Program to check palindrome or not

Program to check armstrong number or not

Get Prime
Method 2 :
In this method we will discuss the recursive way to find the subsets sum, in this either we will take the elements value in the sum or not. Based on this approach we will find the subsets sum.

Method 2 : Code in C
Run
#include <stdio.h>

void subsetSum(int arr[], int l, int r, int sum)
{
    if (l > r) {
        printf("%d ", sum);
        return;
    }
 
    subsetSum(arr, l + 1, r, sum + arr[l]);
 
    subsetSum(arr, l + 1, r, sum);
}
 
int main()
{
    int arr[] = { 4, 3, 5 };
    int n = sizeof(arr) / sizeof(arr[0]);
 
    subsetSum(arr, 0, n - 1, 0);
    return 0;
}
Output
12 7 9 4 8 3 5 0
