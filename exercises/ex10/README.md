# Explore D - Enable Automatic Confirmation

After consistent use, extraction results become reliable enough to skip manual review for high-confidence documents. This exercise shows you how to configure automatic confirmation based on AI confidence scores so routine documents are confirmed without human intervention.

**Pre-requisite:** You need an active schema with at least one processed document. If you have completed [Exercise 3](../ex3/README.md), use **PAYMENT_ADVICE_STANDARD**.

## Steps

1. Navigate to the schema detail for **PAYMENT_ADVICE_STANDARD**, Version 1. Deactivate the schema if it is currently active.

2. Open the **Automation** tab. Toggle **Auto-Confirm** to **ON**. Under **Score for Auto-Confirm**, select **Custom** and enter `75`. The per-field threshold table below updates all fields to 75%.
<br>![](images/04_01_0040.png)

3. Optionally, use the **Set Confidence Threshold** table to raise the threshold for individual fields. For example, slide `paymentAmount` to **90%** to ensure the total is always verified before auto-confirming.

4. Click **Save**, then **Activate** the schema.

5. Upload `payment_advice_acme_jul2026.pdf`. This time the document should skip **Review Needed** and land directly in **Confirmed**: all fields exceeded the 75% threshold.

## Summary

Automatic confirmation eliminates repetitive review work for routine documents while keeping human oversight for low-confidence cases. You can tune thresholds globally or per field to match your accuracy requirements.
