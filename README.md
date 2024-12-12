/*
Program 1: Sine Series Calculation
*/
#include <stdio.h>
#include <math.h>

// Function to calculate factorial
long factorial(int n) {
    long fact = 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    return fact;
}

int main() {
    double x, sum = 0, term;
    int n;

    printf("Enter the value of x (in radians): ");
    scanf("%lf", &x);
    printf("Enter the number of terms: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        term = pow(-1, i) * pow(x, 2 * i + 1) / factorial(2 * i + 1);
        sum += term;
    }

    printf("Sine(%lf) = %lf\n", x, sum);
    return 0;
}

/*
Program 2: Cosine Series Calculation
*/
#include <stdio.h>
#include <math.h>

// Function to calculate factorial
long factorial(int n);

int main() {
    double x, sum = 0, term;
    int n;

    printf("Enter the value of x (in radians): ");
    scanf("%lf", &x);
    printf("Enter the number of terms: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        term = pow(-1, i) * pow(x, 2 * i) / factorial(2 * i);
        sum += term;
    }

    printf("Cosine(%lf) = %lf\n", x, sum);
    return 0;
}

long factorial(int n) {
    long fact = 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    return fact;
}

/*
Program 3: Palindrome Check
*/
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], rev[100];
    int len, flag = 1;

    printf("Enter a string: ");
    scanf("%s", str);

    len = strlen(str);
    for (int i = 0; i < len; i++) {
        rev[i] = str[len - i - 1];
        if (str[i] != rev[i]) {
            flag = 0;
        }
    }

    if (flag)
        printf("%s is a palindrome.\n", str);
    else
        printf("%s is not a palindrome.\n", str);

    return 0;
}

/*
Program 4: Pascal's Triangle
*/
#include <stdio.h>

// Function to calculate factorial
long factorial(int n);

int main() {
    int rows;

    printf("Enter the number of rows for Pascal's triangle: ");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++) {
        for (int j = 0; j <= i; j++) {
            printf("%ld ", factorial(i) / (factorial(j) * factorial(i - j)));
        }
        printf("\n");
    }
    return 0;
}

long factorial(int n) {
    long fact = 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    return fact;
}

/*
Program 5: Matrix Multiplication
*/
#include <stdio.h>

int main() {
    int m, n, p, q;

    printf("Enter the dimensions of the first matrix (rows columns): ");
    scanf("%d %d", &m, &n);
    printf("Enter the dimensions of the second matrix (rows columns): ");
    scanf("%d %d", &p, &q);

    if (n != p) {
        printf("Matrix multiplication not possible.\n");
        return 1;
    }

    int a[m][n], b[p][q], result[m][q];

    printf("Enter elements of the first matrix:\n");
    for (int i = 0; i < m; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    printf("Enter elements of the second matrix:\n");
    for (int i = 0; i < p; i++)
        for (int j = 0; j < q; j++)
            scanf("%d", &b[i][j]);

    // Initialize result matrix to zero
    for (int i = 0; i < m; i++)
        for (int j = 0; j < q; j++)
            result[i][j] = 0;

    // Perform multiplication
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < q; j++) {
            for (int k = 0; k < n; k++) {
                result[i][j] += a[i][k] * b[k][j];
            }
        }
    }

    printf("Resultant matrix:\n");
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < q; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
