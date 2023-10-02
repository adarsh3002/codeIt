#include <stdio.h>

// Merge two sorted subarrays `arr[low...mid]` and `arr[mid+1...high]`
void merge(int arr[], int low, int mid, int high)
{
    int n1 = mid - low + 1; // Size of the left subarray
    int n2 = high - mid;    // Size of the right subarray

    int left[n1], right[n2]; // Temporary arrays to hold the subarrays

    // Copy data to temporary arrays left[] and right[]
    for (int i = 0; i < n1; i++)
    {
        left[i] = arr[low + i];
    }
    for (int j = 0; j < n2; j++)
    {
        right[j] = arr[mid + 1 + j];
    }

    // Merge the two subarrays back into the original array arr[low...high]
    int i = 0, j = 0, k = low;
    while (i < n1 && j < n2)
    {
        if (left[i] <= right[j])
        {
            arr[k] = left[i];
            i++;
        }
        else
        {
            arr[k] = right[j];
            j++;
        }
        k++;
    }

    // Copy the remaining elements of left[] and right[], if any
    while (i < n1)
    {
        arr[k] = left[i];
        i++;
        k++;
    }
    while (j < n2)
    {
        arr[k] = right[j];
        j++;
        k++;
    }
}

// Merge Sort function
void mergeSort(int arr[], int low, int high)
{
    if (low < high)
    {
        int mid = low + (high - low) / 2; // Calculate mid-point

        // Recursively sort the first and second halves
        mergeSort(arr, low, mid);
        mergeSort(arr, mid + 1, high);

        // Merge the sorted halves
        merge(arr, low, mid, high);
    }
}

int main()
{
    int arr[] = {12, 11, 13, 5, 6, 7};
    int arr_size = sizeof(arr) / sizeof(arr[0]);

    printf("Original array: ");
    for (int i = 0; i < arr_size; i++)
    {
        printf("%d ", arr[i]);
    }

    mergeSort(arr, 0, arr_size - 1);

    printf("\nSorted array: ");
    for (int i = 0; i < arr_size; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
