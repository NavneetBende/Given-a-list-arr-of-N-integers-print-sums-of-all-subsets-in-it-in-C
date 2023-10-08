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
