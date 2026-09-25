# Exercise 7 - Build a Multi-Source Schema with Vision Mode

Payment Advice documents fit neatly on one page and are easy to extract. Real enterprise documents are different: a Statement of Work (SOW) can run thirty pages with structured tables buried in exhibits, cover-page metadata that never repeats, and clause text that requires genuine reading rather than pattern matching.

This exercise shows two capabilities that go beyond the basic flow:

- **Vision mode** (`textAndImage`): the model processes every page as an image as well as text, so it can read formatted tables even when the PDF has no underlying text layer — useful for scanned contracts and exhibits.
- **Multi-source merging**: header fields come from the cover page; the Workers table comes from a separate rate-card exhibit. DocAI extracts both in a single pass and merges them into one structured result.

You will create a trimmed SOW schema that captures five cover-page fields and a repeating Workers table, then run it against a sample McKesson-style SOW.

## Exercise 7.1 - Create the Schema

1. From the home screen, click **Manage Schemas**, then **Create**.

2. Fill in the dialog:

   | Field | Value |
   |---|---|
   | Name | `SOW_WORKER_RATES` |
   | Document Type | **Custom** |

   Click **Create**.

## Exercise 7.2 - Configure Vision Mode

The default processing mode uses text only. For documents with formatted tables or low-quality scans, switch to vision mode so the model also processes page images.

1. On the schema version, open the **Processing Settings** tab.

2. Set **Processing Mode** to **Text and Image**.

3. In the **Processing Instructions** field enter:

   ```
   This document is a Statement of Work (SOW). Extract all clause-level information as structured data.
   ```

4. Click **Save**.
<br>![](images/08_02_0010.png)

## Exercise 7.3 - Add the Header Group and Fields

The SOW Header group captures cover-page metadata. All five fields occur exactly once per document.

1. On the **Entities** tab, click **Add**, then **Add Group**. Set:

   | Field | Value |
   |---|---|
   | Name | `header` |
   | Label | `SOW Header` |

   Click **Add**.

2. Add the following fields one at a time. For each, click **Add** then **Add Field**, fill the dialog, and click **Add**:

   | Name | Label | Parent Group | Data Type | Mandatory |
   |---|---|---|---|---|
   | `clientName` | `Client Name` | `header` | String | Yes |
   | `supplierName` | `Supplier Name` | `header` | String | Yes |
   | `effectiveDate` | `Effective Date` | `header` | Date | Yes |
   | `expirationDate` | `Expiration Date` | `header` | Date | No |
   | `parentMsaRef` | `Parent MSA Reference` | `header` | String | No |

3. For each field, click **Edit Settings** and add a Processing Instruction:

   | Field | Processing Instruction |
   |---|---|
   | `clientName` | `Extract the full legal name of the client or buyer entity as it appears in the parties section.` |
   | `supplierName` | `Extract the full legal name of the supplier, staffing agency, or vendor.` |
   | `effectiveDate` | `Extract the date on which the SOW becomes effective. Return in YYYY-MM-DD format.` |
   | `expirationDate` | `Extract the expiry or scheduled end date of this SOW. Return in YYYY-MM-DD format.` |
   | `parentMsaRef` | `Extract the agreement number, date, or title of the Master Services Agreement that governs this SOW.` |

<br>![](images/08_03_0010.png)

## Exercise 7.4 - Add the Workers Table

The Workers table captures one row per worker role defined in the rate-card exhibit. Because this is a table, it repeats: one row per role, not one value per document.

1. Click **Add**, then **Add Table**. Set:

   | Field | Value |
   |---|---|
   | Name | `workers` |
   | Label | `Workers` |

   Click **Add**.

2. Add the following columns to the `workers` table:

   | Name | Label | Data Type | Mandatory | Processing Instruction |
   |---|---|---|---|---|
   | `roleTitle` | `Role Title` | String | Yes | `Extract the exact job title or role name for this worker position as stated in the SOW.` |
   | `roleLevel` | `Level` | String | No | `Extract the seniority level code for this role, such as L1, L2, L3, L4, L5, Senior, or Executive.` |
   | `billRate` | `Bill Rate` | String | Yes | `Extract the bill rate for this role including the currency symbol and time unit, for example 185.00 USD/hr or 1850 USD/day.` |
   | `maxHoursPerWeek` | `Max Hours/Week` | Number | No | `Extract the maximum number of hours per week authorized for this role as a plain number.` |
   | `location` | `Work Location` | String | No | `Extract the work location including city, state, and arrangement type such as remote, hybrid, or on-site.` |
   | `qualifications` | `Qualifications` | String | No | `Extract the minimum qualifications, required certifications, years of experience, and specific skills required for this role.` |

<br>![](images/08_04_0010.png)

3. Click **Activate** to make the schema ready for use.

## Exercise 7.5 - Upload and Extract a Sample SOW

1. From the home screen click **Manage Documents**, then switch to the `SOW_WORKER_RATES` schema.

2. Click **Upload** and select the sample file `sample_mckesson_sow.pdf` from the `documents` folder.

3. Once extraction completes, open the document. Observe:

   - The five header fields are populated from the cover page — **Client Name**, **Supplier Name**, and **Effective Date** in particular.
   - The **Workers** table contains one row per role from the rate-card exhibit, with Bill Rate and Role Title extracted from the formatted table columns.

4. Notice that `billRate` values like `185.00 USD/hr` come from a structured table in an exhibit that may have no selectable text in the PDF — vision mode read the column headers and row values from the rendered image.
<br>![](images/08_05_0010.png)

## Why This Matters

| What the model did | Why it is non-trivial |
|---|---|
| Extracted cover-page fields | Cover page and rate-card exhibit are different pages; fields do not repeat |
| Populated a repeating table | One row per role; number of rows varies by contract |
| Read rates from a formatted table | Bill rate column may exist only as rendered image, not selectable text |
| Merged both sources into one result | Single API call, single extraction job, unified output |

This pattern generalises to any document that mixes a structured summary section with a repeating detail table: purchase orders with line items, insurance policies with coverage schedules, lease agreements with rent escalation tables.

## Summary

You have created a custom schema with vision mode enabled, defined a header group for cover-page fields, and added a repeating Workers table. Continue to [Exercise 8](../ex8/README.md) (coming soon) to explore how this result can feed downstream automation.
