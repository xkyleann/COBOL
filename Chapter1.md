# The Interactive Program

```cobol
        IDENTIFICATION DIVISION.                                                    -> identification division
       *
        PROGRAM-ID. CALC1000.                                                       
       *
        ENVIRONMENT DIVISION.                                                        -> environment division
       *
        INPUT-OUTPUT SECTION.                                                       
       *
        DATA DIVISON.                                                                -> data division              
       *
        FILE SECTION.                                                               
       *
        WORKING-STORAGE SECTION.                                                     
       *
        77 END-OF-SESSION-SWITCH       PIC X               VALUE "N".              
        77 SALES-AMOUNT                PIC 9(5)V99.
        77 SALES-TAX                   PIC Z,ZZZ.99  
       *
        PROCEDURE DIVISION.                                                        -> procedure division  
       *
        000-CALCULATE-SALES-TAX.
              PERFORM 100-CALCULATE-ONE-SALES-TAX
                     UNTIL END-OF-SWITCH = "Y"
              DISPLAY "END OF SESSION."
              STOP RUN.
       *
        100-CALCULATE-ONE-SALES-TAX.
       *
              DISPLAY "---------------------------".
              DISPLAY "TO END PROGRAM, ENTER 0".
              DISPLAY "TO CALCULATE SALES TAX, ENTER THE SALES AMOUNT".
              ACCEPT SALES-AMOUNT.
              IF SALES-AMOUNT = ZERO
                     MOVE "Y" TO END-OF-SESSION-SWITCH
              ELSE
                     COMPUTE SALES-TAX ROUNDED=
                            SALES-AMOUNT * .0785
                     DISPLAY "SALES TAX = " SALES-TAX.             

```

## Summary
- **The identification division** identifies the program by giving program name.
- **The Environment Division** includes the Input-Output Section, which identifies the input and output files used by the program.
- **The Data Division** includes the file section and the Working-Storage Section. 
- **The Procedure Division** contains the program logic it is typically.

# The A and B margins of a COBOL program (Figure 1-5)

| Columns | Purpose     | Remarks     |
| --- | --------------- | --------- |
| **1-6**   | Sequence | A sequence number is added to each coding line when the program is compiled. As a result, the programmer does not enter anything in these positions. |
| **7**   | Indicator | If there is asterisk in thos column. the entire line is treated as a comment. |
| **8-11**   | A margin | Some coding elements (division names, section names, procedure names, 77 level numbers, and 01 level numbers) have to start in this margin. |
| **12-72**   | B margin | Coding lines that do not start in the A margin have to start in this margin. |
| **73-80**   | Identification | identify program |

# How to code the Identification Division –
## The syntax of the Identification Division
```cobol
        IDENTIFICATION DIVISION.
        PROGRAM-ID. program-name.         
```
## An Identification Division with the minimum code
```cobol
        IDENTIFICATION DIVISION.
        PROGRAM-ID. CALC1000.         
```
## An Identification Division that contains comments 
```cobol
         IDENTIFICATION DIVISION.
        *
         PROGRAM-ID. CALC1000.
        *PROGRAMMER.         MIKE MURACH.
        *COMPLETION-DATE.    MARCH 28, 2024.
        *REMARKS.            THIS IS A SIMPLE PROGRAM CALCULATES THE SALES TAX ON AN AMOUNT THAT HAS BEEN ENTERED BY THE USER.   
```

---------------------------------------------------------

# Working Storage Section of the Data Division  (Figure 1-7 )
- **Creating data names** : Max 30 characters in each name 
- **Example** : SALES-AMOUNT and SALES-TAX are better than A1 and B2.
```cobol
         WORKING-STORAGE SECTION.
        *
         77        END-OFF-SESSION-SWITCH         PIC X        VALUE"N".
         77        SALES-AMOUNT                   PIC 9(5)v99.       
         77        SALES-TAX                      PIC Z,ZZZ.99.


```
- **77**: Level number 77 in the Margin A -> data name -> Picture (PIC) clause -> Value Clause in the B margin.
  
### Rules
- Use letters, the digits 0 through 9, and hyphens only.
- Max 30 characters.
- Use at least one letter in the name.






   

