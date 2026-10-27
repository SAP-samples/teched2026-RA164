# RA164 - Hands on SAP Document AI: Next-generation intelligent document processing

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2026-RA164)](https://api.reuse.software/info/github.com/SAP-samples/teched2026-RA164)

## Description

This repository contains the material for the SAP TechEd 2026 session **RA164 - Hands on SAP Document AI: Next-generation intelligent document processing**.

## Overview

In this hands-on session you will configure SAP Document AI end-to-end to process incoming Payment Advice documents. You will activate a pre-built extraction schema, customise it for your business needs, automate the review process, and build a workflow that handles emails with mixed attachments, extracting only the relevant PDF and stamping it with email metadata. A Document Extension workflow then routes high-value payments to a separate approval path.

**Duration:** approximately 60 minutes

## Getting Started

Open the URL provided by your session facilitator and log in with the credentials they shared with you. You will land on the SAP Document AI home screen.

See [SAP Document AI Workspace UI access](exercises/access.md) for the full list of group URLs and user IDs.

From here you can take any path that suits you:
- Follow the **Guided Exercises** below for a structured end-to-end walkthrough.
- Pick one of the **Explore Further** exercises to try out a specific feature independently.
- Bring your own documents and experiment freely.

All sample files can be found in [exercises/documents/](exercises/documents/).

## Guided Exercises

Work through these in order. Each exercise builds on the previous one.

- [Exercise 1 - Set up the Payment Advice schema and process your first document](exercises/ex1/)
- [Exercise 2 - Add a custom field with processing instructions](exercises/ex2/)
- [Exercise 3 - Review documents and enable automatic confirmation](exercises/ex3/)
- [Exercise 4 - Build a Basic workflow for email processing](exercises/ex4/)
- [Exercise 5 - Add an input field and capture email metadata](exercises/ex5/)
- [Exercise 6 - Create a Document Extension workflow with value-based routing](exercises/ex6/)

## Explore Further

Finished early or want to dig deeper? These standalone exercises are independent of the main track. Each one focuses on a single capability and can be completed in any order.

- [Explore A - Build a custom schema from scratch with vision mode](exercises/ex7/)
- [Explore B - Improve extraction accuracy with Instant Learning](exercises/ex8/)
- [Explore C - Auto-generate a schema by uploading a document](exercises/ex9/)

## Sample Documents

| File | Description |
|---|---|
| `payment_advice_acme_jul2026.eml` | Email with 4 attachments, total EUR 48,250 (below 100k) |
| `payment_advice_meridian_sep2026.eml` | Email with 4 attachments, total EUR 113,695 (above 100k) |
| `payment_advice_acme_jul2026.pdf` | Standalone PDF for exercises 1-4 |
| `payment_advice_meridian_sep2026.pdf` | Standalone PDF for exercises 1-4 |
| `Bill of Lading 1.pdf` | Bill of Lading used in Explore B |
| `Bill of Lading 2 FR.pdf` | French Bill of Lading used in Explore B |
| `birth certificate li.pdf` | Birth certificate used in Explore C |
| `Company Registry Extract House of Companies UK.pdf` | Company registry extract used in Explore C |
| `priya_cv.pdf` | CV used in Explore C |
| `SoW.pdf` | Statement of Work used in Explore C |

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support
Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2026 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
