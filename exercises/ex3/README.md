# Exercise 3 - Review Documents

In this exercise you will review and correct a document extracted by SAP Document AI.

## Exercise 3.1 - Review and Correct a Document

1. Open **Manage Documents** for **PAYMENT_ADVICE_STANDARD**. If no document is in **Review Needed** state, upload `payment_advice_acme_jul2026.pdf`. Click the document row to open it.

   The document header shows the current status (**Review Needed**), the confidence score, and key extracted header fields. Click **Edit** to enter review mode.
<br>![](images/04_01_0010.png)

2. The full review screen opens, showing the document preview on the left and the extracted field values on the right. Fields are grouped by section: **Basic Data**, **Business Partner**, and **Amounts**.

   To correct a value using the document preview: click the text directly in the PDF, then in the **Annotation Panel** select the target field from the dropdown, confirm or adjust the value, and click **Apply**.
<br>![](images/04_01_0020.png)

3. Work through any fields flagged with a yellow or red confidence indicator. Once satisfied with all values, click **Save and Confirm**. The document status changes to **Confirmed**.
<br>![](images/04_01_0030.png)

   > **Tip:** Look closely at the **Business Partner Address** field in the **Business Partner** section. On this document the AI may extract the receiving party's address instead of the sender's. This is a good example of where human review catches what automation misses.

## Summary

You have reviewed a document manually and corrected extracted values. Continue to [Exercise 4](../ex4/README.md) to build a workflow that processes emails.
