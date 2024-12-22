#include <stdio.h>
#include <string.h>

void printNameMatrix(char *name) {
    int length = strlen(name);
    int matrixSize = length * 2 - 1; // Size of the square matrix
    char matrix[matrixSize][matrixSize];

    // Initialize the matrix with spaces
    for (int i = 0; i < matrixSize; i++) {
        for (int j = 0; j < matrixSize; j++) {
            matrix[i][j] = ' ';
        }
    }

    // Fill the matrix with the name
    for (int i = 0; i < length; i++) {
        for (int j = i; j < matrixSize - i; j++) {
            matrix[i][j] = name[i];                   // Top
            matrix[matrixSize - i - 1][j] = name[i]; // Bottom
            matrix[j][i] = name[i];                   // Left
            matrix[j][matrixSize - i - 1] = name[i]; // Right
        }
    }

    // Print the matrix
    for (int i = 0; i < matrixSize; i++) {
        for (int j = 0; j < matrixSize; j++) {
            printf("%c ", matrix[i][j]);
        }
        printf("\n");
    }
}

int main() {
    char name[] = "Haris";

    printf("Your name in a complex matrix pattern:\n\n");
    printNameMatrix(name);

    return 0;
}
