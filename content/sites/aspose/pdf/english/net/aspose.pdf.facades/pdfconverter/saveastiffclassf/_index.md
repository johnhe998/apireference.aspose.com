---
title: SaveAsTIFFClassF
second_title: Aspose.PDF for .NET API Reference
description: Converts each pages of a pdf document to images and save images to a single TIFF ClassF file.
type: docs
weight: 170
url: /net/aspose.pdf.facades/pdfconverter/saveastiffclassf/
---
## SaveAsTIFFClassF(string, int, int) {#saveastiffclassf_5}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF file.

```csharp
public void SaveAsTIFFClassF(string outputFile, int imageWidth, int imageHeight)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputFile | String | The stream to save the TIFF image. |
| imageWidth | Int32 | The image width, the unit is pixel. |
| imageHeight | Int32 | The image height, the unit is pixel. |

### Examples

```csharp
[C#]
PdfConverter converter = new PdfConverter();
converter.BindPdf(@"D:\Test\test.pdf");
converter.DoConvert();
converter.SaveAsTIFFClassF(@"D:\Test\test.tiff",204,196);	

[Visual Basic]
Dim converter As PdfConverter =  New PdfConverter() 
converter.BindPdf("D:\Test\test.pdf")
converter.DoConvert()
converter.SaveAsTIFFClassF(@"D:\Test\test.tiff",204,196)
```

### See Also

* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

---

## SaveAsTIFFClassF(string, PageSize) {#saveastiffclassf_4}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF file.

```csharp
public void SaveAsTIFFClassF(string outputFile, PageSize pageSize)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputFile | String | The stream to save the TIFF image. |
| pageSize | PageSize | The page size of the image. |

### See Also

* class [PageSize](../../../aspose.pdf/pagesize)
* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

---

## SaveAsTIFFClassF(Stream, int, int) {#saveastiffclassf_2}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF stream.

```csharp
public void SaveAsTIFFClassF(Stream outputStream, int imageWidth, int imageHeight)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputStream | Stream | The stream to save the TIFF image. |
| imageWidth | Int32 | The image width, the unit is pixel. |
| imageHeight | Int32 | The image height, the unit is pixel. |

### See Also

* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

---

## SaveAsTIFFClassF(Stream, PageSize) {#saveastiffclassf_1}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF stream.

```csharp
public void SaveAsTIFFClassF(Stream outputStream, PageSize pageSize)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputStream | Stream | The stream to save the TIFF image. |
| pageSize | PageSize | The page size of the image. |

### See Also

* class [PageSize](../../../aspose.pdf/pagesize)
* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

---

## SaveAsTIFFClassF(string) {#saveastiffclassf_3}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF file.

```csharp
public void SaveAsTIFFClassF(string outputFile)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputFile | String | The stream to save the TIFF image. |

### Examples

```csharp
[C#]
PdfConverter converter = new PdfConverter();
converter.BindPdf(@"D:\Test\test.pdf");
converter.DoConvert();
converter.SaveAsTIFFClassF(@"D:\Test\test.tiff");	

[Visual Basic]
Dim converter As PdfConverter =  New PdfConverter() 
converter.BindPdf("D:\Test\test.pdf")
converter.DoConvert()
converter.SaveAsTIFFClassF(@"D:\Test\test.tiff")
```

### See Also

* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

---

## SaveAsTIFFClassF(Stream) {#saveastiffclassf}

Converts each pages of a pdf document to images and save images to a single TIFF ClassF stream.

```csharp
public void SaveAsTIFFClassF(Stream outputStream)
```

| Parameter | Type | Description |
| --- | --- | --- |
| outputStream | Stream | The stream to save the TIFF image. |

### See Also

* class [PdfConverter](../../pdfconverter)
* namespace [Aspose.Pdf.Facades](../../pdfconverter)
* assembly [Aspose.PDF](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.PDF.dll -->
