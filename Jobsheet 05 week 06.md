#  JobSheet 5 ( Week 6) Basic Programming
 Student Information
* **Name** :  Muhammad Talha
* **Program**: Informatics Engineering
* **Student ID** : 264107020089
  
  ----

  ## 1. Objectives
  1. Students can solve problems and case studies using nested selection statements.
  2. Students can apply nested selection statements in Java programs.
  3. Students can apply the logical operators &&, ||, and ! in selection structures.

## 2.1 Experiment 1: 
A student wants to register for the thesis exam. The SIMTA system first checks an administrative
requirement: the student must have no outstanding penalties. If this requirement is met, the system
then checks the guidance log. To register for the exam, the student must have at least 8 guidance
sessions with Supervisor 1 and at least 4 guidance sessions with Supervisor 2. If all requirements are
met, the student can proceed to register for the thesis exam. If not, the system shows the reason for
failure.

### The Code for the above case Study is:

```java
import  java.util.Scanner;
public class NestedThesisExam24 {
    public static void main(String[] args) {
        Scanner sc = new Scanner (System.in);

        String massage;
        System.out.println("Has the Student cleared all penalties ? (Yes /No) ");
        String noPenalty = sc.nextLine().trim();

        //  the "trim()" here uesed for the removing leading and trailing spaces form the String

        // now get the input form users about the guigance session with first and second supervisor

        System.out.println("Enter the total number of the sessions with Supervisors 1 : ");
        int guidanceCOunt1 = sc.nextInt();
        System.out.println("Enter the total number of sessions with supervisors 2 :");
        int guidanceCount2 = sc.nextInt();

        // now used the nested If 

        if (noPenalty.equalsIgnoreCase("yes")) {
             if (guidanceCOunt1 >= 8 && guidanceCount2 >= 4) {
                massage = "All the reqirments met. The Student may ragister for the theseis exam! ";

             } else if ( guidanceCOunt1 < 8 && guidanceCount2 < 4) {
                massage = " Faild! the Guidance session with Supervisor 1 are bwlow then 8 and Supervisor 2 are below then 4";

             } else if (guidanceCOunt1 <8){
                massage = "Failed! Guidance session with Supervisor 1 have not reached 8";
             } else {
                massage = "Failed! Guidance session with Supervisor 2 have not reached 4";

             }

        } else {
            massage = "Failed! the student Still have and outstanding penalty  ";
        }
        System.out.println(massage);   }
        
}
```

#### Out put:

   Has the Student cleared all penalties ? (Yes /No) 
   
        yes 
        
   Enter the total number of the sessions with Supervisors 1 : 
   
         9
         
   Enter the total number of sessions with supervisors 2 :
   
         4
         
   All the reqirments met. The Student may ragister for the theseis exam! 
   

#### Questions

1. What happens if the student answers "No" to the penalty-clearance question? Why?
2. Explain the meaning of the following code snippet!
if (guidanceCount1 >= 8 && guidanceCount2 >= 4) {
3. Describe the full flow of checking the student's requirements from start to finish. Explain
step by step for every condition!

#### Answers: 
  1. if the student enter the "no" the program still getting the input form the urses and also it will exicute the program but the the condation will exicute directly about the " failed massage" rather if the usres gives the input value of the Supervisor 1 and 2 more the or equal to 8 and 4.
    
 2. in the frist condtion "if (guidanceCount1 >= 8 && guidanceCount2 >= 4" mean the inatianl condation for the nested if. if one of them not meat the condation the it will goes directly to the final else condation and print the "massage",.

   3.  Flow of the program

    1---> Assing the value of the String and store it in String
    2--->  get the input form the student that he clear all penalties or not
    3---> get the input form the urse about the spuervisor 1 and 2  total meeting.
    4----> apply the nasted if  
         a---> if the noperalty is clear then goes for the second if conditon insied the nasted if conditons 
        b---> and the they apply and check the condition of the meeting with Supervisores
        c---> if one of them is less then the required then it will print the messing massage for it.
       d---> this one is for the last massage if the student is penaolty then the elas condition will directly exicute
      e---> still confues about the last simple out put of the println massage*/

----
## 2.2. Experiment 2: Logical Operators to Determine Campus WiFi Access
 
The campus WiFi can only be used by students or lecturers whose accounts are not blocked. The
program receives information on whether the user is a student, whether the user is a lecturer, and
whether the user's account is currently blocked. Access is granted if the user is a student or a lecturer,
and the account is not blocked. This experiment practices the logical operators && (AND), || (OR), and
! (NOT).

#### Code for the above case study is:
``` java
import java.util.Scanner;
public class LogicalOperatorWifi24 {
    public static void main(String[] args) {
        // import the scanner library 
        Scanner sc = new Scanner (System.in);
        // declare three boolean
        boolean isStudent, islecturer, isBlocked;
        // take input form the users for all three boolean
        System.out.println("Is the User a Student? (true/ false )");
        isStudent = sc.nextBoolean();
        System.out.println("Is the user a Lecturer? (true / false");
        islecturer = sc.nextBoolean();
        System.out.println("Is the usres account currently blocked? (true/ false");
        isBlocked = sc.nextBoolean();

        // now bulid the if --- else condation for the wifi access.
        if ((isStudent && islecturer) && !isBlocked) {
            System.out.println("Wifi access garanted");

        } else {
            System.out.println("Wifi access denide");
        }
    }
}
```

#### Out put:
      Is the User a Student? (true/ false )
      
         true
         
      Is the user a Lecturer? (true / false
      
         false
         
      Is the usres account currently blocked? (true/ false
      
          true
          
      Wifi access denide

 -----
      
#### Questions
1. Explain the function of the ||, &&, and ! operators in the condition above.
2. Why can a lecturer still get access when isStudent = false?
3. Change || to &&. Run the program again using test data 1 and 2. What happens, and why?
4. In the expression isStudent || isLecturer, when does isLecturer not need to be
evaluated? Explain using short-circuit evaluation.
5. In the expression (isStudent || isLecturer) && !isBlocked, when does !isBlocked
not need to be evaluated? Explain.

    Test    |  isStudent  |  isLecturer   |   isBlocked

    1       |    true     |     false     |     false

    2       |   false     |     true      |     false

    3       |   true      |     false     |     true

    4       |   false     |     false     |     false

#### Answers:
1. The || (OR) operator checks whether the user is a student or a lecturer (or both) — it returns true if at least one role matches. The ! (NOT) operator reverses the value of isBlocked, so !isBlocked becomes true only when the user is not blocked. The && (AND) operator then combines both results — the user is only granted wifi access if both conditions are true at the same time: they hold a valid role (student or lecturer) and their account is not blocked. If either part is false — no valid role, or the account is blocked — the whole condition becomes false, and access is denied.

  2. bcs the logical OR oporatoer is used for both if the student false the lacturer is true .

 3. if we replace "&& insted of the ||" so if one of the condation false in the student and lecturer then it will give the false so the condation fail for geting the access. but this condaiton is not valid for the above senario bcs at the same time the one person can't be as student or lecturer.

  4. in java the short circuit ecaluation act like if " ||" oporator is it then the java see the first value is true or not is yes then they evaluate it. and if its "&&" condaiton the java short circut oprator see if the frist value is false then they avaluate it false atoumaticaly. in the above condation if the student true then || result is true if the student false then it see the second value of lecturer then five the final result. if it true then && will see the another value if its true to the final resul is true other wise false.

 5.  if the ((isStudent || is lecturer) && !isBlocked) if the both of the value of student and lecturer is false. so the java short circuit ecaluation is if the frist part or value is false then java skip the rest part. and NOt isblocked value is true then give the final value of the false.

-----


## 2.3. Experiment 3: Nested IF and Logical Operators to Determine Laboratory Access
----
 
A student may use the laboratory outside class hours if their status is active and they are not currently
under sanction. If this requirement is met, the system performs a second check. Laboratory access is
granted if the student has lecturer permission or is a lab assistant. This case combines nested selection
with logical operators.


#### Code for the above case study is:
``` java
import java.util.Scanner;
public class NestedLabAccess024 {
    public static void main(String[] args) {
        Scanner sc = new Scanner (System.in);
        // declare the variables 
        boolean isActiveStudent, isSanctionde, hasLecturerPermit, isLabAssistant ;

        // get the input form the users 

        System.out.println("\tEnter your current status are you Active Student now : (true/ false) ");
        isActiveStudent = sc.nextBoolean();
          System.out.println("\tEnter your current status are you sanctioned now : (true/ false) ");
        isSanctionde= sc.nextBoolean();
          System.out.println("\tEnter your current status are you Lectures permit now : (true/ false) ");
        hasLecturerPermit = sc.nextBoolean();
          System.out.println("\tEnter your current status are you Lab Assistant now : (true/ false) ");
        isLabAssistant = sc.nextBoolean();

        // apply the nasted if condaiton 

        if (isActiveStudent && !isSanctionde) {
            if (hasLecturerPermit || isLabAssistant) {
                System.out.println("Laboratory access garanted");
            } else {
                System.out.println("Access Denied: lecturer permsiison or lave assistant status required ");
            }
        }else {
            System.out.println("Access desnid: student does not meet the requirment");
        }

    }
    
}

```

#### Out Put:
        Enter your current status are you Active Student now : (true/ false) 
        
true

        Enter your current status are you sanctioned now : (true/ false) 
        
false

        Enter your current status are you Lectures permit now : (true/ false) 
        
true

        Enter your current status are you Lab Assistant now : (true/ false) 
        
false

        Laboratory access granted


#### Questions
1. Why is the check hasLecturerPermit || isLabAssistant placed inside the first IF?
2. Explain the function of the &&, ||, and ! operators in this program.
3. Can the access requirement be written as a single condition: isActiveStudent &&
!isSanctioned && (hasLecturerPermit || isLabAssistant)? Explain whether the
final access decision stays the same.
4. What is the advantage of using Nested IF in this case, compared to a single IF, if the system
needs to show different reasons for denial?
5. Create one input combination that causes access to be denied at the first level, and one that
causes it to be denied at the second level.


#### Answers:
 1.the has lecturer and lab Assistant is plaed inside the frist if bcs we want to know if the student get the permsion access form the one of condation from it or not if yes then the result is evaluated. other wise not. this is enter the frist if of nestaed bcs we want to confrim frist the student is active or seconited 
        
2. the funcation of && , || , ! operatoes in this program is to get the natiianl statues of student is it active or not and if true. then if he is secctioned aslo then the NOT oparator chane it. ||  is used for the permission of the lab access if he have the one value true then then nested if condation will exicute.

3. yes it will work the same but the issue here in the quesation they asked us about to use the nestead if condation.

4.Nested if lets you show different denial messages depending on where the failure happens — a single combined condition can only say "access denied" with no detail on why. The nested structure has a separate else at each level, so it can distinguish "not eligible" from "missing permission."

    
     Denied at 1st level (outer fails):
     isActiveStudent = false
     isSanctioned = false
     hasLecturerPermit = true
     isLabAssistant = false

    → Output: "Access denied: student does not meet the requirement"
     (inner if never runs, since outer already failed)

     Denied at 2nd level (outer passes, inner fails):
      isActiveStudent = true
      isSanctioned = false
      hasLecturerPermit = false
      isLabAssistant = false

      → Output "Access Denied: lecturer permission or lab assistant status required"
         (outer passes, but neither permit condition is true) */

----


                
## 3. Assignments
1. Implement the flowchart you created in Exercise 2 of Week 6 for the bookstore discount
system as a Java program. The program must use nested selection statements (Nested IF).
Use logical operators where needed

2. Write a Java program for a lab-assistant candidate selection system based on the following
rules:
a. A student may take part in the selection if their status is active and they are not
currently under academic sanction.
b. If this requirement is met, the student must also meet the next requirement: a minimum
grade of 80 in Basic Programming, or a programming competency certificate.
c. If both requirements are met, the student will be called for an interview. The student is
accepted as an assistant if the interview score is at least 75.
d. The program must show the reason if the student fails at any stage of the selection.
e. Use nested selection and logical operators. Save the file as
Task2AssistantSelectionAttendanceNo.java.

### Program Code of 3.1:
``` java
 import java.util.Scanner;
public class Task2BookDiscount24 {
    public static void main(String[] args) {
        Scanner input = new Scanner (System.in);
        // Declare the variables
        double bookPrice;
        int numberOfBooks;
        int typeOfBook;
        double discountPercentage = 0;
        double totalPayment;
        double totalDiscount;
        String nameOfDay;

        System.out.println("\t ----> wellcome to Our BookStore <----");
        System.out.print("\t Enter the name of the day (e.g., Monday, Tuesday, etc.): ");
        nameOfDay = input.next();
        System.out.print("\t Enter the Type of Book (1 = Dictionary, 2 = Novel, 3 = othertype): ");
        typeOfBook = input.nextInt();
        System.out.print("\tEnter the quantity of books you want to purchase: ");
        numberOfBooks = input.nextInt();
        System.out.print("\tEnter the price of the book: $ ");
        bookPrice = input.nextDouble();

        // Calculate the total payment before discount
           totalPayment = bookPrice * numberOfBooks;
           System.out.printf("\t Total payment before discount: $ %.2f%n", totalPayment); // disply only two dicimal points

         if (nameOfDay.equalsIgnoreCase("Wednesday")){
            if (typeOfBook == 1) {
                discountPercentage = 0.10;
                if (numberOfBooks > 2) {
                    discountPercentage += 0.02;
                }
            }else if (typeOfBook == 2) {
                discountPercentage = 0.07;
                if (numberOfBooks > 3) {
                    discountPercentage += 0.01;
                }
            } else if (typeOfBook == 3) {
                discountPercentage = 0.00;
                if (numberOfBooks > 5) {
                    discountPercentage += 0.05;
                }
            } else {
                System.out.println("Invalid book type.");
            }
        }

        // Calculate the total discount and final payment
        totalDiscount = totalPayment * discountPercentage;
        totalPayment -= totalDiscount;
        System.out.printf("\t Total discount: $ %.5f%n", totalDiscount); // only 5 decimal points
        System.out.printf("\t Final payment: $ %.2f%n", totalPayment);
}
}

```
#### Out put of the above program:
    ----> wellcome to Our BookStore <----
        Enter the name of the day (e.g., Monday, Tuesday, etc.): wednesday
        
        Enter the Type of Book (1 = Dictionary, 2 = Novel, 3 = othertype): 2
        
        Enter the quantity of books you want to purchase: 5
        
        Enter the price of the book: $ 45
        
           Total payment before discount: $ 225.00
           
           Total discount: $ 18.00000
           
                Final payment: $ 207.00


#### 3.2: 
``` java
import java.util.Scanner;
public class Task2AssistantSelection24 {
    public static void main (String [] args){
        Scanner input = new Scanner(System.in);
        // first i have to assing the variables 

    boolean avtiveStudent;
    double gradsBP;
    boolean certificatePogrammingCompetency;
    int interviewScore;

    System.out.println("\tEnter the student status (true for active, false for inactive): ");
    avtiveStudent = input.nextBoolean();
    System.out.println("\tEnter the Grads in Basic Programming (0 - 100): ");
    gradsBP = input.nextDouble();
    System.out.println("\tEnter the certificate status for Programming Competency (true for yes, false for no): ");
    certificatePogrammingCompetency = input.nextBoolean();
    System.out.println("\tEnter the interview score (0 - 100): ");
    interviewScore = input.nextInt();

    // now i have to use the Nasted if else statement to check the conditions for the student selection

    // also i will show the reson for the failure stage of the student selection
   /*  if (avtiveStudent) {
        if (gradsBP >= 80 && certificatePogrammingCompetency) {

            if (interviewScore >= 75) {
                System.out.println("The student is selected for the program.");
            } else {
                System.out.println("The student is not selected due to low interview score.");
            }
                

    } else {
        System.out.println("The student is not selected due to inactive status.");
} }*/

         if (avtiveStudent) {
            if (gradsBP >= 80 && certificatePogrammingCompetency) {
                if (interviewScore >= 75) {
                    System.out.println("The student is selected for the program.");
                } else {
                    System.out.println("The student is not selected due to low interview score.");
                }
            } else {
                System.out.println("\t ---- SOORY ! The student is not selected due to insufficient grades or missing certificate.------");
            }
        } else {
            System.out.println("\t ---- SOORY ! The student is not selected due to inactive status.------");
        }
    }
}
```
#### Outpu:
        Enter the student status (true for active, false for inactive): 
 true
 
        Enter the Grads in Basic Programming (0 - 100): 
86

        Enter the certificate status for Programming Competency (true for yes, false for no): 
true

        Enter the interview score (0 - 100): 
75

The student is selected for the program.

        

                
