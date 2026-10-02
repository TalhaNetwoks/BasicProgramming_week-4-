#  JobSheet 4 ( Week 5) Basic Programming
 Student Information
* **Name** :  Muhammad Talha
* **Program**: Informatics Engineering
* **Student ID** : 264107020089
  
  ----

  ## 1. Objectives
1. Students are able to solve problems/case studies using simple selection syntax
2. Students are able to apply simple selection syntax in a Java program

## 2.1 Experiment 1: Using IF and IF-ELSE to Print the KRS
At the beginning of every semester, students must print their KRS (Study Plan Card) so it
can be signed by their Academic Advisor (DPA). SIAKAD will check the student's UKT (tuition
fee) payment status. If the student has fully paid the UKT, the system shows the KRS so it can
be printed

### The Code for the above case Study is:

```java
import java.util.Scanner;

public class SelectionIf24 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("-----Print KRS SIAKAD-----");
        System.out.println("Has the UKT been Paid?  (true/false): ");
        boolean uktpaid = sc.nextBoolean();
        
        // now we have to apply the condition if the uktpaid is true or false
        if (uktpaid) {
            System.out.println("UKT payment Verified");
            System.out.println("Please print your KRs and ask your DPA to sign it");
        }
        else {
            System.out.println("UKT payment not verified");
            System.out.println("Reistration rejected. Please pay your UKT first");
        }    }
        
}
```

#### Out put:

![The program output](<C:/Users/HP/Downloads/Basic Programing/Week 4/Program Photos/2.1.png> "the output")

#### Questions
1. What value must you enter so that both lines inside the IF block are printed? Explain
why only that value is accepted!
2. Run the program, then enter false. Which lines are printed and which lines are not?
Explain the execution flow when the IF condition is false!
3. Run the program, then enter TRUE (in capital letters) and yes. What happens with
each input? If the program stops with an error, explain the cause!

//1. inside the IF block we enter the condition if the uktpaid as boolean so, if the urse input data is true the the program will print the massage inside the IF block (both line will be pritn).we put the boolean variable inside the IF block. so oIF bock execute only if the condition is true. if the condition is false then the IF block will not execute and the program will not print the massage inside the IF block.
 
// 2. inside the ELSE block we enter the condition if the uktpaid as boolean so, if the urse input data is false the then the program will print the massage inside the ELSE block (both line will be pritn).we put the boolean variable inside the ELSE block. so ELSE bock execute only if the condition is false. if the condition is true then the ELSE block will not execute and the program will not print the massage inside the ELSE block.

//3. if we try to run the program using the input "TRUE" isted of "true" the program in my laptop is still running and it print the massage inside the IF block. and the other when i gives the "yes" so it gives me the error massage "Exception in thread "main" java.util.InputMismatchException" and the program is not running. so we have to give the input as "true" or "false" only. bcs of the boolean data type. if we give the input as "yes" or "no" the program will not run and it will give the error massage. so we have to give the input as "true" or "false" only.

//4. the above is the example of the IF ELSE block. if the condition is true then the IF block will execute and if the condition is false then the ELSE block will execute. so we can say that the IF ELSE block is used to check the condition and execute the block of code based on the condition.

----
## 2.2. Experiment 2: SWITCH-CASE to Print the KRS
At the beginning of every semester, students must print their KRS so it can be signed by
their Academic Advisor (DPA). The SIAKAD system will check the student's current semester,
then show the KRS for that semester so it can be printed.

#### Code for the above case study is:
``` java
import java.util.Scanner;
public class SelectioSwitch24 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("-----Print KRS SIAKAD-----");
        System.out.println("Enter your Current Semester :");

        int semester = sc.nextInt();
        switch (semester) {
            case 1:
                System.out.println("KRS for Semester 1 is Displayed");
                break;
            case 2:
                System.out.println("KRS for Semster 2 is Displayed");
                break;
            case 3:
                System.out.println("KRS for Semester 3 is Displayed");
                break;
            case 4:
                System.out.println("KRS for Semester 4 is Displayed");
                break;
            case 5:
                System.out.println("KRS for Semester 5 is Displayed");
                break;case 6:
                System.out.println("KRS for Semester 6 is Displayed");  
                break;
            case 7:
                System.out.println("KRS for Semester 7 is Displayed");
                break;
            case 8:
                System.out.println("KRS for Semester 8 is Displayed");
                break;
                default:
                System.out.println("Invalid Semester");


        }
    }
}
```
#### Questions
1. Delete the break; statement in case 5, then compile and run the program again with
the input 5. Write down the output, then explain the function of break in the
SWITCH-CASE structure based on your experiment! Put the code back to how it was
when you are done.
2. Run the program with the input 10, then with the input 0. What is the output of these
two runs? Based on the results, explain the role of default and what will happen to
the program if the default part is deleted!
3. Change the data type of the semester variable to double, then compile the program.
Does the program compile successfully? Write down the error message and explain its
cause. List the data types that can be used as the expression in a switch!
4. Create a new file named SelectionIfElseAttendanceNo.java. Convert the KRS printing
program that uses SWITCH-CASE into an IF - ELSE IF - ELSE form. The program output
must be exactly the same as the SWITCH-CASE version, including for invalid input. In
your opinion, which one is easier to read for this case, and why?

#### Answers:
              //1. if i delete the "break;" from the case 5 then the will not stop it will jump to the next case 6 and it will be executed and then the program will stop. so we have to put the "break;" after each case so that the program will stop after executing the case. the funcation of break is to stop the program after executing the case. and the changes is now done as it was before.

                // 2. with the input of "10 and 0" the program will print the "Invalid Semester" bcs its not in the range or 1 - 8. so base on the result the role of the default is to print the result you want to print if the input is not in the range of the case. so the default is used to print the result if the input is not in the range of the case.
                
                //3. when i change the data type of the variable semester from int to double it gives the error massage case constants in a switch on 'double' are not of type 'double'. so we have to change the data type of the variable semester from double to int. so the changes is now done as it was before. and the data types that can be used in the switch statement are byte, short, char, int, String and enum types. so we have to use the data type of the variable semester as int.
                
                //4. we can check this answer in the file name "SelectionIfElse24.java".
                





