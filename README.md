#include <stdio.h>
float totalSavings(float savings[], int n) {
    if (n == 0)
        return 0;
    else
        return savings[n - 1] + totalSavings(savings, n - 1);
}

int main() {
    int n, i;
    float savings[12], total = 0, average;
    printf("Enter number of months (1 to 12): ");
    if (scanf("%d", &n) != 1 || n <= 0 || n > 12) {
        printf("Please enter a number between 1 and 12.\n");
        return 0;
    }
    printf("\nEnter savings for each month (in ₹):\n");
    for (i = 0; i < n; i++) {
        printf("Month %d: ₹", i + 1);
        if (scanf("%f", &savings[i]) != 1) {
            printf("Only numbers allowed! Please enter a number.\n");
            return 0;
        }
    }
    total = totalSavings(savings, n);
    average = total / n;
    printf("Total savings = ₹%.2f\n", total);
    printf("Average per month = ₹%.2f\n", average);
    return 0;
}
   
