# EXPERIMENT 21
# Aim
# Software Used
Visual Studio Code
# Theory
1. Binary Search:

Binary search is a search algorithm that determines the position of the desired value in a sorted array. It works by repeatedly dividing the search interval in half until the desired value is found or the interval is empty. The search interval is decreased in half by comparing the chosen element to the search space's middle value.
To apply Binary Search algorithm, the data structure must be sorted.

2. Linear Search:

Linear search is a method for finding an element within a collection of elements. To find the desired element, linear search visits each element of the collection one by one in a sequential order. Linear search is also referred to as sequential search.

Linear Search iterates over all of the elements in the array and checks to see if the current element is equal to the desire element. If we find an element that is equal to the desired element, we return the index of the current element. Otherwise, if no element matches the target element, return -1 because the element was not found.

CODES:

1. Binary Search
```
#include <iostream>
using namespace std;

int binarySearch(int arr[], int size, int target) {
    int low = 0, high = size - 1;
    
    while (low <= high) {
        int mid = low + (high - low) / 2; 
        if (arr[mid] == target)
            return mid;
        if (arr[mid] < target)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}
int main() {
    int arr[] = {2, 3, 4, 10, 40}; 
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 10;
    int result = binarySearch(arr, size, target);
    if (result != -1)
        cout << "Element found at index " << result << endl;
    else
        cout << "Element not found in array" << endl;
        
    return 0;
}
```
o/p:
![Screenshot 2024-10-22 203218](https://github.com/user-attachments/assets/e496d72d-5f8d-42a2-8135-e7c4f912c5e8)


2. Linear Search
```
 #include <iostream>
using namespace std;

// Function for linear search
int linearSearch(int arr[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == target) {
            return i; // Return the index if target is found
        }
    }
    return -1; // Return -1 if the target is not found
}

int main() {
    int arr[] = {2, 3, 4, 10, 40}; // Unsorted or sorted array
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 10;
    
    int result = linearSearch(arr, size, target);
    
    if (result != -1)
        cout << "Element found at index " << result << endl;
    else
        cout << "Element not found in array" << endl;
        
    return 0;
}
```
o/p:


![Screenshot 2024-10-22 203253](https://github.com/user-attachments/assets/da1bf06f-2153-4c81-bdfc-3f25841583df)


# Conclusion
Binary search is faster with a time complexity of O(log n) but only works on sorted arrays, making it ideal for large datasets. Linear search, though slower with O(n) complexity, works on both sorted and unsorted arrays, offering more flexibility for smaller or unsorted datasets.
