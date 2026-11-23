#include <stdio.h>

int main(void) {
    char op;
    double num1, num2;

    printf("Enter an operator (+, -, *, /, %%): ");
    if (scanf(" %c", &op) != 1) {
        return 1;
    }

    printf("Enter two numbers: ");
    if (scanf("%lf %lf", &num1, &num2) != 2) {
        return 1;
    }

    switch (op) {
        case '+':
            printf("Result: %.2lf\n", num1 + num2);
            break;
        case '-':
            printf("Result: %.2lf\n", num1 - num2);
            break;
        case '*':
            printf("Result: %.2lf\n", num1 * num2);
            break;
        case '/':
            if (num2 == 0.0) {
                printf("Error: Division by zero is not allowed.\n");
            } else {
                printf("Result: %.2lf\n", num1 / num2);
            }
            break;
        case '%': {
            long long a = (long long)num1;
            long long b = (long long)num2;
            if (b == 0) {
                printf("Error: Modulus by zero is not allowed.\n");
            } else {
                printf("Result: %lld\n", a % b);
            }
            break;
        }
        default:
            printf("Error: Invalid operator.\n");
            break;
    }

    return 0;
}
