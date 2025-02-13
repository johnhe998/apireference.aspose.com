---
title: PdfFontEmbeddingMode
linktitle: PdfFontEmbeddingMode
second_title: Aspose.Words for Java
description: Specifies how Aspose.Words should embed fonts in Java.
type: docs
weight: 476
url: /java/com.aspose.words/pdffontembeddingmode/
---

**Inheritance:**
java.lang.Object
```
public class PdfFontEmbeddingMode
```

Specifies how Aspose.Words should embed fonts.
## Fields

| Field | Description |
| --- | --- |
| [EMBED_ALL](#EMBED-ALL) | Aspose.Words embeds all fonts. |
| [EMBED_NONE](#EMBED-NONE) | Aspose.Words do not embed any fonts. |
| [EMBED_NONSTANDARD](#EMBED-NONSTANDARD) | Aspose.Words embeds all fonts excepting standard Windows fonts Arial and Times New Roman. |
| [length](#length) |  |
## Methods

| Method | Description |
| --- | --- |
| [fromName(String pdfFontEmbeddingModeName)](#fromName-java.lang.String) |  |
| [getName(int pdfFontEmbeddingMode)](#getName-int) |  |
| [getValues()](#getValues) |  |
| [toString(int pdfFontEmbeddingMode)](#toString-int) |  |
### EMBED_ALL {#EMBED-ALL}
```
public static int EMBED_ALL
```


Aspose.Words embeds all fonts.

### EMBED_NONE {#EMBED-NONE}
```
public static int EMBED_NONE
```


Aspose.Words do not embed any fonts.

### EMBED_NONSTANDARD {#EMBED-NONSTANDARD}
```
public static int EMBED_NONSTANDARD
```


Aspose.Words embeds all fonts excepting standard Windows fonts Arial and Times New Roman. Only Arial and Times New Roman fonts are affected in this mode because MS Word doesn't embed only these fonts when saving document to PDF.

### length {#length}
```
public static int length
```


### fromName(String pdfFontEmbeddingModeName) {#fromName-java.lang.String}
```
public static int fromName(String pdfFontEmbeddingModeName)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| pdfFontEmbeddingModeName | java.lang.String |  |

**Returns:**
int
### getName(int pdfFontEmbeddingMode) {#getName-int}
```
public static String getName(int pdfFontEmbeddingMode)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| pdfFontEmbeddingMode | int |  |

**Returns:**
java.lang.String
### getValues() {#getValues}
```
public static int[] getValues()
```




**Returns:**
int[]
### toString(int pdfFontEmbeddingMode) {#toString-int}
```
public static String toString(int pdfFontEmbeddingMode)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| pdfFontEmbeddingMode | int |  |

**Returns:**
java.lang.String
