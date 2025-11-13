#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int roll;
    float marks[5];
    float total;
    float average;
    char grade;
};

char calculateGrade(float avg) {
    if (avg >= 90)
        return 'A';
    else if (avg >= 75)
        return 'B';
    else if (avg >= 60)
        return 'C';
    else if (avg >= 40)
        return 'D';
    else
        return 'F';
}

int main() {
    struct Student s[50];
    int n;
    const char *subjects[5] = {"Mathematics", "Science", "English", "History", "Computer"};

    printf("Enter number of students: ");
    scanf("%d", &n);
    getchar(); // consume newline

    for (int i = 0; i < n; i++) {
        printf("\n========== Enter details for Student %d ==========\n", i + 1);
        printf("Enter Name: ");
        fgets(s[i].name, sizeof(s[i].name), stdin);
        s[i].name[strcspn(s[i].name, "\n")] = '\0'; // remove newline

        printf("Enter Roll Number: ");
        scanf("%d", &s[i].roll);

        s[i].total = 0;
        printf("Enter marks (out of 100):\n");
        for (int j = 0; j < 5; j++) {
            printf("  %s: ", subjects[j]);
            scanf("%f", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }

        s[i].average = s[i].total / 5.0;
        s[i].grade = calculateGrade(s[i].average);

        getchar(); // consume newline before next input
    }

    // Marksheet Header
    printf("\n\n============================================================\n");
    printf("                      STUDENT MARKSHEET                     \n");
    printf("============================================================\n");

    for (int i = 0; i < n; i++) {
        printf("\n------------------------------------------------------------\n");
        printf("Name       : %s\n", s[i].name);
        printf("Roll No.   : %d\n", s[i].roll);
        printf("------------------------------------------------------------\n");
        printf("Subject\t\t\tMarks\n");
        printf("------------------------------------------------------------\n");

        for (int j = 0; j < 5; j++) {
            printf("%-15s\t%.2f\n", subjects[j], s[i].marks[j]);
        }

        printf("------------------------------------------------------------\n");
        printf("Total Marks : %.2f / 500.00\n", s[i].total);
        printf("Average     : %.2f\n", s[i].average);
        printf("Grade       : %c\n", s[i].grade);
        printf("------------------------------------------------------------\n");

        if (s[i].grade == 'F')
            printf("Result: FAIL\n");
        else
            printf("Result: PASS\n");

        printf("============================================================\n");
    }

    return 0;
}
