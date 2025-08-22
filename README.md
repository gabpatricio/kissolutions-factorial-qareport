# kissolutions-factorial-qareport
# The Greatest Factorial Calculator - Quality Assurance Report
> **Analyst**: Gabriela Patricio
> **Report Date**: August 22nd, 2025
---
## Summary
While the core factorial calculation works for valid integers, the application is **not ready** for public release.
Testing revealed critical bugs in error handling for invalid inputs and user interface, including incorrect navigation links and UX lacking basic features for usability. From an user's perspective, the application is straightforward for "happy path" scenarios. However, its quality degrades significantly when an user makes a mistake. For example, while using the factorial calculator, it becomes inconvenient to manually clear the input field or interpret results when recalculating. 
Recommendations for bug fixes and enhancements are detailed below.

---
## Suggestions and recommended enhancements
Expected results: improves usability and prevents user errors.
* **[S-01] Add a "Clear" Button:** Add a `Clear` button next to `Calculate!` so the user can easily reset the input field.
* **[S-02] Auto-Clear Previous Results:** Auto-clear previous results each time the user clicks Calculate! again, ensuring the current output corresponds only to the latest calculation.
* **[S-03] Align Page Title:** Change the title text on top of the main input label to "The Greatest Factorial Calculator" so it aligns with stakeholder expectations.

## Bugs Identified
Prioritized by severity to guide the development team on what to fix first.

* **[B-01]** No error message while inputing a negative integer
* **[B-02]** No result or error message when calculating a large number
* **[B-03]** Terms and Conditions redirects to the wrong page
* **[B-04]** Privacy redirects to the wrong page
* **[B-05]** Website title fix

## Test Cases 
**Regarding the main functionality**

|Step|Action|Expected Result|Actual Result|Step Result|
| :--- | :--- | :--- | :--- | :--- |
|1|Insert a **positive integer (5)** in the calculator's input field and click "Calculate!"|The result should be displayed as `120`|The result is displayed as "The factorial of 5 is: `120`"|Passed|
|2|Insert a **negative integer (-5)** in the calculator's input field and click "Calculate!"|The result should be an error message|There is no error message, and if it there was another calculation before, it keeps the result of the previous step|**Failed**|
|3|Insert a **zero (0)** in the calculator's input field and click "Calculate!"|The result should be displayed as `1`|The result is displayed as `1`|Passed|
|4|Insert a **decimal (4.2)** in the calculator's input field and click "Calculate!"|The result should be an error message|The result is the error message `Please enter an integer`|Passed|
|5|Insert a **string (fghjd)** in the calculator's input field and click "Calculate!"|The result should be an error message|The result is the error message `Please enter an integer`|Passed|
|6|Leave an **empty** space in the calculator's input field and click "Calculate!"|The result should be an error message|The result is the error message `Please enter an integer`|Passed|
|7|Insert an **emoji ⚠️** in the calculator's input field and click "Calculate!"|The result should be an error message|The result is the error message `Please enter an integer`|Passed|
|8|Insert an **unexpected string of characters used in coding, such as <>** in the calculator's input field and click "Calculate!"|The result should be an error message|The result is the error message **Please enter an integer**|Passed|
|9|Insert a **large number (1000)** in the calculator's input field and click "Calculate!"|The result should be displayed as a `scientific notation` or a message such as `value too large`, or `infinite value`|There is no error message, and if it there was another calculation before, it keeps the result of the previous step|**Failed**|

**Regarding front-end functionalities and UX**
|Step|Action|Expected Result|Actual Result|Step Result|
| :--- | :--- | :--- | :--- | :--- |
|1|Check the website title|It should read `The Greatest Factorial Calculator`|It reads as `Factoriall`|**Failed**|
|2|Check if Terms and Conditions is written properly|It should read `Terms and Conditions`|It reads as `Terms and Conditions`|Passed|
|3|Check if Terms and Conditions redirects to the correct page|It should redirect to the `Terms and Conditions` page|It redirects to the `Privacy` page|**Failed**|
|4|Check if Privacy is written properly|It should read `Privacy`|It reads as `Privacy`|Passed|
|5|Check if the Privacy page redirects to the correct page|It should redirect to the `Privacy` page|It redirects to the `Terms and Conditions` page|**Failed**|



