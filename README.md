NAME:T.K.SHRIVIMAL


REF NO:212224220101

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
int main()
{
    float length, width, area;
    float *plength=&length, *pwidth=&width, *parea=&area;
    scanf("%f", &length);
    scanf("%f", &width);
    *parea = *plength * (*pwidth);
    printf("Area of rectangle = %f sq. units ", *parea);
    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/41cc08c7-0b39-4ae0-a81a-c5e673abd322)
       	


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
    str = (char*) malloc(5 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }
    strcpy(str, "Welcome");
    printf("%s", str);

    free(str);
    return 0;
}

```
## OUTPUT

![image](https://github.com/user-attachments/assets/d0c59350-0fb9-4e87-bd4d-be36c741b9fc)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.
 




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
	int rollNumber;
	float marks;
};
int main() {
	struct Student student;
	scanf("%s", student.name);
	scanf("%d", &student.rollNumber);
	scanf("%f", &student.marks); 
	printf("Displaying Information:\n");
	printf("Name: %s\n", student.name);
	printf("Roll number: %d\n", student.rollNumber);
	printf("Marks: %.1f\n", student.marks); 
	return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/a4805e4c-464f-4ea4-85b8-7db9ac944c1d)


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
#include<stdio.h>
struct employee{
    int empno;
    char dept[50];
    int basic_pay;
}e[3];

int main(){
    for(int i=0;i<3;i++){
        scanf("%d %s %d",&e[i].empno,e[i].dept,&e[i].basic_pay);
    }
    printf("Details of the Employee:\n");
    int da,hra;
    float gs;
    for(int i=0;i<3;i++){
        da = e[i].basic_pay * 0.1;
        hra = e[i].basic_pay * 0.3;
        gs = e[i].basic_pay + da + hra;
        printf("%d %s %d %d %d %.2f\n",e[i].empno,e[i].dept,e[i].basic_pay,da,hra,gs);
    }
}
```

 ## OUTPUT
![image](https://github.com/user-attachments/assets/7e11a1c2-96fc-43f8-a47c-5dc47634a152)

 

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
};

int main() {
    struct student s[2];
    int i, j;

    for (i = 0; i < 2; i++) {
        scanf("%s", s[i].name);
        scanf("%d", &s[i].rollno);
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }
    for (i = 0; i < 2; i++) {
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
    }
    for (i = 0; i < 2; i++) {
        printf("\nStudent Name: %s\n", s[i].name);
        printf("Roll Number: %d\n", s[i].rollno);
        printf("Total Marks: %d\n", s[i].total);
        printf("Average Marks: %.2f\n", s[i].total / 5.0);
    }
    return 0;
}
```


## OUTPUT

 ![image](https://github.com/user-attachments/assets/0894b928-9376-4c40-96ca-f008b1415bf1)

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


