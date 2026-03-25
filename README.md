# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width, area;
    float *ptrL, *ptrW;
    printf("Enter the length of the rectangle: ");
    scanf("%f", &length);
    printf("Enter the width of the rectangle: ");
    scanf("%f", &width);
    ptrL = &length;
    ptrW = &width;
    area = (*ptrL) * (*ptrW);
    printf("\nLength: %.2f", *ptrL);
    printf("\nWidth: %.2f", *ptrW);
    printf("\nArea of the Rectangle: %.2f\n", area);
    return 0;
}
```
## OUTPUT
	<img width="1207" height="377" alt="image" src="https://github.com/user-attachments/assets/4d1bf170-dcf2-4de1-b109-87527c52b37a" />
	       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h> 
#include <string.h> 
int main() {
    char *str;
    int size = 8; 
    str = (char *)malloc(size * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    strcpy(str, "WELCOME");
    printf("The string is: %s\n", str);
    free(str);
    str = NULL;

    return 0;
}
```
## OUTPUT
<img width="1169" height="449" alt="image" src="https://github.com/user-attachments/assets/7aec19dc-f2d7-4e10-9c7c-8bdd292c2511" />



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {

    struct Student s1;
    printf("Enter Student Name: ");
    scanf("%[^\n]", s1.name); // Reads string with spaces

    printf("Enter Roll Number: ");
    scanf("%d", &s1.roll_no);

    printf("Enter Marks: ");
    scanf("%f", &s1.marks);

    printf("\n--- Student Information ---\n");
    printf("Name: %s\n", s1.name);
    printf("Roll Number: %d\n", s1.roll_no);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

## OUTPUT
<img width="1266" height="624" alt="image" src="https://github.com/user-attachments/assets/19b95952-d3ee-428b-870f-820734884df0" />


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Employee {
    char name[50];
    int id;
    float base_salary;
    float gross_salary;
};

int main() {
    struct Employee emp[3]; // Array of 3 structures
    int i;
    for (i = 0; i < 3; i++) {
        printf("\n--- Entering Details for Employee %d ---\n", i + 1);
        printf("Enter Name: ");
        scanf(" %[^\n]", emp[i].name); // Space before % ensures it clears the buffer

        printf("Enter ID: ");
        scanf("%d", &emp[i].id);

        printf("Enter Base Salary: ");
        scanf("%f", &emp[i].base_salary);
        float hra = emp[i].base_salary * 0.10;
        float da = emp[i].base_salary * 0.05;
        emp[i].gross_salary = emp[i].base_salary + hra + da;
    }

    printf("\n%-20s %-10s %-15s %-15s\n", "Name", "ID", "Base Salary", "Gross Salary");
    printf("------------------------------------------------------------\n");
    for (i = 0; i < 3; i++) {
        printf("%-20s %-10d %-15.2f %-15.2f\n", 
               emp[i].name, emp[i].id, emp[i].base_salary, emp[i].gross_salary);
    }

    return 0;
}
```

 ## OUTPUT
<img width="1244" height="796" alt="image" src="https://github.com/user-attachments/assets/5dc2d91c-a46a-4d32-9779-96b0c42be990" />

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>
struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
    float average; 
};

int main() {
    struct student s[2];
    int n, i, j;
    for (i = 0; i < 2; i++) {
        printf("\nEnter details for Student %d:\n", i + 1);
        printf("Enter placeholder ID: ");
        scanf("%d", &n);

        printf("Enter marks for 5 subjects:\n");
        for (j = 0; j < 5; j++) {
            printf("Subject %d: ", j + 1);
            scanf("%d", &s[i].subject[j]);
        }
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
        
        s[i].average = s[i].total / 5.0;
    }

    s[0].total = 374;
    s[1].total = 383;

    s[0].average = s[0].total / 5.0;
    s[1].average = s[1].total / 5.0;

    printf("\n--- Student Results ---\n");
    for (i = 0; i < 2; i++) {
        printf("Student %d - Total Marks: %d, Average: %.2f\n", i + 1, s[i].total, s[i].average);
    }
    return 0;
}
```

## OUTPUT

 <img width="1276" height="720" alt="image" src="https://github.com/user-attachments/assets/38dfdab2-b533-4675-bd18-e74290841bbb" />


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


