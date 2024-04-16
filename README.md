# Health ID Coding Test

## Introduction

Healthcare facilities, professionals, and groups often require unique identifiers to ensure proper identification, streamline operations, and facilitate efficient communication. These identifiers can range from registration numbers for facilities to license numbers for healthcare workers and patient/client identifiers for patients.

Given a alpha numeric patient identifier format `XXXYYYYZ-MM` where X and Z are upper case (capital) letters, while Y are numbers, M is a code that indicates male `01` or female `02`. this alpha numeric identifier is know to be incremental and cannot repeate for 2 individuals. For example, Given EUQ0021S-01 for a male patient, the next identifier for any patient would be EUQ0021T-01. the increment starts from the right alphabet `Z` from [A-Z] and proceeds to the integer `Y` from [0001 - 9999], then lastly the alphabet 'X' from [AAA-ZZZ]. 
Given the patient Identifer for a female patient GUS0001Z-02, the next patient would get GUS0002A-02 for female and GUS0002A-01 for male
Given the patient Identifer GUS9999A-02, the next patient would get GUS9999B-02 for female and GUS9999B-01 for male
Given the patient Identifer GUS9999A-02, the next patient would get GUS9999B-02 for female and GUS9999B-01 for male
Given the patient Identifer FUQ9999Z-02, the next patient would get FUR0001Z-02 for female and FUR0001Z-01 for male
Given the patient Identifer ZZZ9999Z-02, the next patient would get an error as this is the last numeber in this serries

*In Context, The number of combination of patient identifiers generated using this ID system is roughtly 26 × 26 × 26 × 10 × 10 × 10 × 10 × 26 which is 17,576,000,000*

## Requirements
Write a program that assign an identifier to a patient for an EMR system.
Your program should be able to `Assign` an Identifier and `Issue` a new Identifier given an alphanumeric stringrepresenting the last assigned ID number.

1. Your program must accept two input commands passed with space delimited arguments.
2. "**Assign**" will register a new patient with the supplied identifier.
    * Assign will be called as follows:
        * `Assign GUQ0034T-01 Seretse Goitsebeng Peter` or `Assign HJY9890T-02 Maphiri Khama`
        * Note that anything after the ID number is considered the name. In this case the Id numbers are 'UQ0034T-01' and 'HJY9890T-02' and the namea are 'Seretse Goitsebeng Peter' and 'Maphiri Khama'.
    * Note that Assign *should not* print anything to STDOUT while the program is executing. It should only print 'on exit.' which you can include as a command, write out to a text file or implement on exit of the application.
3. "**Issue**" will take in a patient identifier and a Sex and then print out the patient identifier that follows the given identifier.
  * Issue will be called as follows:
    * Issue MNG9922A-02 Male. This should print MNG9922B-01 to STDOUT.
    * Issue WOD9999Z-02 Female. This should print WOE9999Z-02 to STDOUT.
    * Issue TCN1000A-01 Female. This should print TCN1000B-02 to STDOUT.
    * The identifier ZZZ9999Z-02 should print "error" to STDOUT since it is the last possible identifier.
4. When all input has been read and processed, a report should be generated and written to STDOUT in the format shown
in the example below.
5. The summary should include the name of each registered person followed by a colon and their patient identifier followed by a colon and their Sex.
6. The names should be displayed alphabetically.

## Restrictions

- Numbers start from 0001 and increase up to 9999, 0000 is not used

## Input Assumptions

- All input will be valid and space-delimited. So do not check or validate inputs

## Examples

### Example 1:
Give the commands
```
Issue TCN1000A-02 Male
Assign GUQ0034T-01 Mamat Buhbash
Assign DSR7548W-02 Kolos Imi . C
```

the system should output
```
TCN1000B-01
```

then on exit outputs
```
Kolos Imi . C: DSR7548W-02: Female
Mamat Buhbash: GUQ0034T-01: Male
```


### Example 2:
Give the commands
```
Assign NHU0001A-01 John Doe
Issue KLM0001A-01 Male
Assign KLM9999Z-02 Jane Smith
Issue KLM9999Z-02 Female
Issue ZZZ9999Z-02 Male
Assign NHJ0002A-01 Alice Johnson
Issue HJY9890T-02 Male
```

the system should output
```
KLM0001B-01
KLN9999A-02
error
HJY9890U-01
```

then on exit outputs
```
Alice Johnson: NHJ0002A-01: Male
Jane Smith: KLM9999Z-02: Female
John Doe: NHU0001A-01: Male
```


## Submission

While a production-ready application is not required, we encourage you to submit your best effort. We understand your time constraints and commitments
You can submit your coding solution in one of two ways.
1. By emailing a compressed (zip) `HealthID_YourName.zip` file with all of your files to the recruiter that sent you the coding test. Note that .RAR or class files will not be accepted or executed due to security.
2. By sending a git repo of the project to the email


## Implementing and Packaging Your Solution:

Implement your solution with any of VB.NET, C# or Java. Please write automated tests and include them with your submission.

Your solution will be assessed on correctness.

In addition to your code and tests, please also include a README that explains:

- An overview of your design decisions
- How to run your code and tests, including how to compile it if applicable and how to install any dependencies your code may have.

Good Luck!
