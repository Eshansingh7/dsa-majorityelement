#include <stdio.h>

int findMajorityElement(int arr[], int size) {
    int majorityElement = -1;
    int count = 0;

    for (int i = 0; i < size; i++) {
        if (count == 0) {
            majorityElement = arr[i];
            count = 1;
        } else if (arr[i] == majorityElement) {
            count++;
        } else {
            count--;
        }
    }

    count = 0;
    for (int i = 0; i < size; i++) {
        if (arr[i] == majorityElement) {
            count++;
        }
    }

    if (count > size / 2) {
        return majorityElement;
    } else {
        return -1;
    }
}

int main() {
    int arr[] = {2, 4, 5, 5, 5, 5, 5};
    int size = sizeof(arr) / sizeof(arr[0]);

    int majorityElement = findMajorityElement(arr, size);

    if (majorityElement != -1) {
        printf("Majority Element: %d\n", majorityElement);
    } else {
        printf("No majority element found.\n");
    }

    return 0;
}
