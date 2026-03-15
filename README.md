# Mini-Project-on-Arrays-using-C-Language 

<br>
Author ~ Mohammed Feroz
<br>
This is My 1st Repository :  C program demonstrating dynamic memory allocation using malloc and realloc. It creates an array, takes user input, resizes the array dynamically, allows adding new elements if the size increases, prints the updated array, and calculates the sum of all elements.


#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr ;
    int n, newSize,i;

    printf("Enter the n of the array: ");
    scanf("%d", &n);

    arr = (int *)malloc(n * sizeof(int));
    if (arr == NULL) {
        return 1;
    }

    printf("Enter %d elements: ", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("The array elements are: ");
    for (i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    printf("Enter new size for the array: ");
    scanf("%d", &newSize);

    arr = (int *)realloc(arr, newSize * sizeof(int));
    

    if (newSize > n) {
        printf("Enter %d new elements: ", newSize - n);
        for (i = n; i < newSize; i++) {
            scanf("%d", &arr[i]);
        }
    }

    printf("The array after resizing is: \n");
    for (i = 0; i < newSize; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

   int sum = 0;
    for (i = 0; i < newSize; i++) {
        sum += arr[i];
    }
    printf("Sum of all elements: %d\n", sum);

    free(arr);
    return 0;
}


