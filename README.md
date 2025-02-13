# CDuce Ontology Transformation and Validation

## Overview
This repository contains experiments and tools for transforming and validating ontologies using CDuce. We have tested different versions of CDuce to analyze its behavior with simple ontologies, encountering specific issues that are documented below.

## Issues Encountered
### 1. Namespace Handling in the Latest Development Version
- The latest development version correctly produces an `Undefined namespace prefix` error when namespaces are missing.
- However, it introduces a new issue: when loading an XML file, placeholder namespaces (e.g., `ns1`) appear in the parsed output, even when explicit namespaces have been defined.
- Different namespaces (e.g., `owl` and `rdf`) are both mapped to `ns1`, making them indistinguishable and preventing proper parsing.

### 2. Stable Version Works as Expected
- The stable version (`0.6.1-rc1`) correctly recognizes all namespaces, whether explicitly defined or inferred from the XML schema.
- It allows parsing the XML file without errors.

### 3. Unexpected Internal Error in the Latest Development Version
- Executing lines 83-113 in `transform_internal_error.cd` triggered an internal error (`Todo: 35`).
- The absence of a proper backtrace suggests that this feature might still be under development.

## Next Steps
Due to these issues, we are currently limited to using the stable version, despite its known limitations. We seek clarification on:
- Whether there is a new way to represent data, meaning that our ontology definitions need to be updated.
- Whether this issue is related to the CDuce compiler itself.

## CDuce Syntax Highlighting Extension
We also want to mention that we have created an extension for Visual Studio Code to improve the development experience with CDuce.
You can find it at the link:

[CDuce Syntax Highlighting](https://marketplace.visualstudio.com/items?itemName=FurTh3r.cduce-syntax-highlighting)

### Features
- Provides syntax highlighting for CDuce keywords, types, and operators.
- Supports strings, numbers, comments, and more.

### Installation
1. Open Visual Studio Code.
2. Go to the Extensions view (`Ctrl+Shift+X`).
3. Search for `CDuce Syntax Highlighting`.
4. Click `Install`.

### Usage
Once installed, you can start editing CDuce files (`.cd` extension), and syntax highlighting will be applied automatically.

**Note:** This extension is still in an early stage and may require refinements, but it helps improve readability and ease development.
