#  JobSheet 4 ( Week 5) Basic Programming
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
#### Questions
1. Explain the function of the ||, &&, and ! operators in the condition above.
2. Why can a lecturer still get access when isStudent = false?
3. Change || to &&. Run the program again using test data 1 and 2. What happens, and why?
4. In the expression isStudent || isLecturer, when does isLecturer not need to be
evaluated? Explain using short-circuit evaluation.
5. In the expression (isStudent || isLecturer) && !isBlocked, when does !isBlocked
not need to be evaluated? Explain.
Test    isStudent    isLecturer     isBlocked
1        true           false           false
2        false          true            false
3        true           false           true
4        false          false           false

#### Answers:
    1. The || (OR) operator checks whether the user is a student or a lecturer (or both) — it returns true if at least one role matches. The ! (NOT) operator reverses the value of isBlocked, so !isBlocked becomes true only when the user is not blocked. The && (AND) operator then combines both results — the user is only granted wifi access if both conditions are true at the same time: they hold a valid role (student or lecturer) and their account is not blocked. If either part is false — no valid role, or the account is blocked — the whole condition becomes false, and access is denied.

  2. bcs the logical OR oporatoer is used for both if the student false the lacturer is true .

 3. if we replace "&& insted of the ||" so if one of the condation false in the student and lecturer then it will give the false so the condation fail for geting the access. but this condaiton is not valid for the above senario bcs at the same time the one person can't be as student or lecturer.

  4. in java the short circuit ecaluation act like if " ||" oporator is it then the java see the first value is true or not is yes then they evaluate it. and if its "&&" condaiton the java short circut oprator see if the frist value is false then they avaluate it false atoumaticaly. in the above condation if the student true then || result is true if the student false then it see the second value of lecturer then five the final result. if it true then && will see the another value if its true to the final resul is true other wise false.

 5.  if the ((isStudent || is lecturer) && !isBlocked) if the both of the value of student and lecturer is false. so the java short circuit ecaluation is if the frist part or value is false then java skip the rest part. and NOt isblocked value is true then give the final value of the false.

                
## 3. Assignments
1. Open the file SelectionIfAttendanceNo.java again. Change the IF-ELSE selection
structure in the program into a Ternary Operator, with the following rules:
a. The decision result is first stored in a String variable named message, then printed
using a single System.out.println() statement
b. The program output must be exactly the same as the original program
c. Save it with the file name Assignment1SelectionAttendanceNo.java
In your opinion, when is the Ternary Operator better to use than IF-ELSE, and when
should it not be used?
2. Look at the following flowchart.

   
A KRS system validates the number of credits (SKS) taken by a student, where the
maximum number allowed is 24 credits. Implement the flowchart above as a Java
program using an IF-ELSE selection structure, then save it with the file name
Assignment2SelectionAttendanceNo.java!
4. In the Basic Programming class, you made flowcharts and pseudocode for two cases on
the Exercise slides (page 33). Now implement both of them in Java, with the following
rules.
a. For Problem 1 — Parking System, use an IF-ELSE selection structure and name the file
AssignmentParkingAttendanceNo.java
b. For Problem 2 — Academic Queue Machine, use a SWITCH-CASE selection structure
and name the file: AssignmentQueueAttendanceNo.java. In addition, the program
must include a default part to handle codes outside 1–4 with the message "Service
code is not available

### Program Code of 3.1:
``` java
 import java.util.Scanner;
public class Assignment1Selection24 {
    public static void main (String [] args ) {
        Scanner input = new Scanner (System.in);

        System.out.println("----- Print KRS SIAKAD ----");
        System.out.println("Has the UKT been paid? (true /false) ");
        boolean uktpaid = input.nextBoolean();

        // tarnory oporetor 
        String massage = (uktpaid)? "UKT payment is verified. please aske your DPA and sing your KRS form him" : " please do your KRS payments first";
        System.out.println(massage);

        input.close();
    }
}
```
#### Questions:
a. The decision result is first stored in a String variable named message, then printed
using a single System.out.println() statement
b. The program output must be exactly the same as the original program
c. Save it with the file name Assignment1SelectionAttendanceNo.java
In your opinion, when is the Ternary Operator better to use than IF-ELSE, and when
should it not be used?

#### Answer:
// according to my opinon the tarnory oporatoer is good for the short logic and the if elas is best for the complax cases.


### Flow Chart and write a program for it.
A KRS system validates the number of credits (SKS) taken by a student, where the
maximum number allowed is 24 credits. Implement the flowchart above as a Java
program using an IF-ELSE selection structure, then save it with the file name
Assignment2SelectionAttendanceNo.java!

``` java

import java.util.Scanner;
public class Assignment2Selection24 {
    public static void main (String [] args){
        
        /*Scanner input = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = input.nextInt();

        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
            */

        // acordding to the flow chart frist we have to declear the value

        int totalCredits;
        Scanner input= new Scanner(System.in);
        // input the totalcredits
        totalCredits = input.nextInt();
        if (totalCredits >= 24) {
            System.out.println("Exceeds the lismits.");
        } else {
            System.out.println("KRS is Valid.");
        }

    }
}
```
##### Hints:

        // this is to much simple and esay to understand the if else statement and the ternary operator is good for the short logic and the if else is best for the complex cases.


### Question 3: 
 In the Basic Programming class, you made flowcharts and pseudocode for two cases on
the Exercise slides (page 33). Now implement both of them in Java, with the following
rules.
a. For Problem 1 — Parking System, use an IF-ELSE selection structure and name the file
AssignmentParkingAttendanceNo.java
b. For Problem 2 — Academic Queue Machine, use a SWITCH-CASE selection structure
and name the file: AssignmentQueueAttendanceNo.java. In addition, the program
must include a default part to handle codes outside 1–4 with the message "Service
code is not available"

#### 3.1
``` java

import java.util.Scanner;
public class AssignmentParking24 {
    public static void main (String [] args) {

    // use the if-ELSE case to make the car parking System, if the car is parked in the parking lot, it will be charged a fee, if not, it will be free.

    int parkingFee = 2000;
    int parkedHours;
    int moreHoures;

    Scanner input = new Scanner (System.in);

    System.out.print("\n ----- Salamt Datang to Malang Shopping Center parking lot ----- ");
    System.out.println("\t Please Enter the number of hours you car will be parked : ");
    parkedHours = input.nextInt();  

    // if more hours so the fee must be more then it 1000 RP for each hour, if less than 2 hours so the fee is free.

      if (parkedHours > 2 ){
        moreHoures = ((parkingFee) + ( parkedHours - 2) * 1000);
        System.out.println(" \tyour car is parked for the "+ parkedHours+" hours");
        System.out.println ("\tSo, your parking fee is Rp. "+ moreHoures);
    }  else 
    {
        System.out.println(" \tyour car is parked for the "+ parkedHours+" hours");
        System.out.println("\tSo, your parking fee is Rp. 0");
    }

    }
    
}
```

#### output 

   // ----- Salamt Datang to Malang Shopping Center parking lot -----
   
   Please Enter the number of hours you car will be parked :
   
                  4
                  
        your car is parked for the 4 hours
        
        So, your parking fee is Rp. 4000

#### 3.2: 
``` java
import java.util.Scanner;
public class AssignmentQueue24 {
    public static void main (String [] args){
// use the switch case to make the student serive counters

        Scanner input = new Scanner(System.in);
        System.out.println("----- Student Service Counters -----");
        System.out.println("Please select the service you need: ");
        System.out.println("1. Certification of Diplomas");
        System.out.println("2. Certificate of Enrollment");
        System.out.println("3. Tuition Fee Payment");
        System.out.print("4. Application for Academic Leave ");

        System.out.print("\nEnter your choice (1-4): ");
        int choice = input.nextInt();
        // switch case to make the student service counters
        switch (choice){
            case 1:
                System.out.println("You have selected Certification of Diplomas");
                break;
            case 2:
                System.out.println("You have selected Certificate of Enrollment");
                break;
            case 3:
                System.out.println("You have selected Tuition Fee Payment");
                break;
            case 4:
                System.out.println("You have selected Application for Academic Leave");
                break;
            default:
                System.out.println("Invalid choice. Serviece code is not avlible .");
        }

        

    }
    
}

```
#### Outpu:
----- Student Service Counters -----

Please select the service you need: 
1. Certification of Diplomas
2. Certificate of Enrollment
3. Tuition Fee Payment
4. Application for Academic Leave
   
Enter your choice (1-4):  3

You have selected Tuition Fee Payment


        

                
