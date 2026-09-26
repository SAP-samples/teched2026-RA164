# RA164 - Hands on SAP Document AI: Next-generation intelligent document processing

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2026-RA164)](https://api.reuse.software/info/github.com/SAP-samples/teched2026-RA164)

## Description

This repository contains the material for the SAP TechEd 2026 session **RA164 - Hands on SAP Document AI: Next-generation intelligent document processing**.

## Overview

In this hands-on session you will configure SAP Document AI end-to-end to process incoming Payment Advice documents. You will activate a pre-built extraction schema, customise it for your business needs, automate the review process, and build a workflow that handles emails with mixed attachments — extracting only the relevant PDF and stamping it with email metadata. A Document Extension workflow then routes high-value payments to a separate approval path.

**Duration:** approximately 60 minutes

## Exercises

- [Getting Started](exercises/ex0/)
- [Exercise 1 - Activate the Payment Advice schema and process your first document](exercises/ex1/)
- [Exercise 2 - Add a custom field with processing instructions](exercises/ex2/)
- [Exercise 3 - Review documents and enable automatic confirmation](exercises/ex3/)
- [Exercise 4 - Build a Basic workflow for email processing](exercises/ex4/)
- [Exercise 5 - Add an input field and capture email metadata](exercises/ex5/)
- [Exercise 6 - Create a Document Extension workflow with value-based routing](exercises/ex6/)
- [Exercise 7 - Build a multi-source schema with vision mode](exercises/ex7/)

## Sample Documents

All sample files are in [exercises/documents/](exercises/documents/).

| File | Description |
|---|---|
| `payment_advice_acme_jul2026.eml` | Email with 4 attachments, total EUR 48,250 (below 100k) |
| `payment_advice_meridian_sep2026.eml` | Email with 4 attachments, total EUR 113,695 (above 100k) |
| `payment_advice_acme_jul2026.pdf` | Standalone PDF for exercises 1-4 |
| `payment_advice_meridian_sep2026.pdf` | Standalone PDF for exercises 1-4 |

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support
Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2026 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
