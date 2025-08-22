# kissolutions-factorial-qareport
The Greatest Factorial Calculator - Quality Assurance Report

## Summary
While the core factorial calculation works for valid integers, the application is **not ready** for public release.
Testing revealed critical bugs in error handling for invalid inputs and user interface, including incorrect navigation links and UX lacking basic features for usability. From an user's perspective, the application is straightforward for "happy path" scenarios. However, its quality degrades significantly when an user makes a mistake. For example, while using the factorial calculator, it becomes inconvenient to manually clear the input field or interpret results when recalculating. 
Recommendations for bug fixes and enhancements are detailed below.


## Suggestions
Expected results: improves usability and prevents user errors.

1 Add a clear button next to the Calculate! button, so the user can reset the input field without manually deleting its contents.
2 Auto-clear previous results each time the user clicks Calculate! again, ensuring the current output corresponds only to the latest calculation.
3 Change the title to The Greatest Factorial Calculator, so it aligns to what it is expected from our stakeholders

## Bugs Identified
Prioritized by severity to guide the development team on what to fix first.

1 No error message while inputing a negative integer
2 No result or error message when calculating a large number
3 Terms and Conditions redirects to the wrong page
4 Privacy redirects to the wrong page
5 Website title fix

## Test Cases 
**Regarding the main functionality**

**Step**             **Action**                                                   **Expected result**                            **Actual result**                       **Step Result**
1                    Insert a **positive integer (5)** in the calculator's        The result should be displayed as **120**      The result is displayed as              Passed
                     input field and click "Calculate!"                                                                          "The factorial of 5 is: **120**"                                                                                                                  

2                    Insert a **negative integer (-5)** in the calculator's       The result should be an error message          There is no error message, and if it   
                     input field and click "Calculate!"                                                                          there was another calculation before,   Failed
                                                                                                                                 it keeps the result of the previous 
                                                                                                                                 step

3                    Insert a **zero (0)** in the calculator's input field        The result should be displayed as **1**        The result is displayed as **1**        Passed
                     and click "Calculate!"

4                    Insert a **decimal (4.2)** in the calculator's input field   The result should be an error message          The result is an error message          Passed
                     and click "Calculate!"                                                                                      **Please enter an integer**

5                    Insert a **string (fghjd)** in the calculator's input field  The result should be an error message          The result is an error message          Passed
                     and click "Calculate!"                                                                                      **Please enter an integer**

6                    Leave an **empty** space in the calculator's input field     The result should be an error message          The result is an error message          Passed
                     and click "Calculate!"                                                                                      **Please enter an integer** 

7                    Insert an **emoji ⚠️** in the calculator's input field       The result should be an error message          The result is an error message          Passed
                     and click "Calculate!"                                                                                      **Please enter an integer**

8                    Insert an **unexpected string of characters used in 
                     coding, such as <>** in the calculator's input field         The result should be an error message          The result is an error message          Passed
                     and click "Calculate!"                                                                                      **Please enter an integer**

9                    Insert a **large number (1000)** in the calculator's         The result should be displayed as              There is no error message, and if it    
                     input field and click "Calculate!"                           a **scientific notation** or a message         there was another calculation before,   Failed
                                                                                  such as **value too large**, or                it keeps the result of the previous 
                                                                                  **infinite value**                             step

**Regarding front-end functionalities and UX**
**Step**             **Action**                                                   **Expected result**                             **Actual result**                  **Step Result**
1                    Check the website title                                      It should read "The Greatest Factorial          It reads as Factoriall             Failed
                                                                                  Calculator"
2                    Check if Terms and Conditions is written properly            It should read "Terms and Conditions"           It reads as Terms and Conditions   Passed

3                    Check if Terms and Conditions redirects to the correct page  It should redirect to the Terms and Conditions  It redirects to the Privacy page   Failed
                                                                                  page
                                                                                  
4                    Check if Privacy is written properly                         It should read "Privacy"                        It reads as Privacy                Passed   

5                    Check if the Privacy page redirects to the correct page      It should redirect to the Privacy page          It redirects to the Terms and      Failed
                                                                                                                                  Conditions page



