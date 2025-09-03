# TheA and B margins of a COBOL program

```cobol
       IDENTIFICATION DIVISION.
       PROGRAM-ID. TAXCALC.

       DATA DIVISION.
       WORKING-STORAGE SECTION.
       77  END-OF-SESSION-SWITCH   PIC X        VALUE " ".
       77  SALES-AMOUNT            PIC 9(5)V99.
       77  SALES-TAX               PIC 9(3)V99.

       PROCEDURE DIVISION.
       100-CALCULATE-SALES-TAX.
           PERFORM 100-CALCULATE-ONE-SALES-TAX
               UNTIL END-OF-SESSION-SWITCH = "Y".
           DISPLAY "END OF SESSION.".
           STOP RUN.
```
