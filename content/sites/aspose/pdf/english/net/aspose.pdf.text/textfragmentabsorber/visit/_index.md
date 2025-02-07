---
title: Visit
second_title: Aspose.PDF for .NET API Reference
description: Performs search on the specified page.
type: docs
weight: 140
url: /net/aspose.pdf.text/textfragmentabsorber/visit/
---
## Visit(Page) {#visit_1}

Performs search on the specified page.

```csharp
public override void Visit(Page page)
```

| Parameter | Type | Description |
| --- | --- | --- |
| page | Page | PDF document page object. |

### Examples

The example demonstrates how to find text on the first PDF document page and replace the text.

```csharp
// Open document
Document doc = new Document(@"D:\Tests\input.pdf");

// Find font that will be used to change document text font
Aspose.Pdf.Txt.Font font = FontRepository.FindFont("Arial");

// Create TextFragmentAbsorber object to find all "hello world" text occurrences
TextFragmentAbsorber absorber = new TextFragmentAbsorber("hello world");

// Accept the absorber for first page
absorber.Visit(doc.Pages[1]);

// Change text of all search occurrences
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.Text = "hi world";
}

// Save document
doc.Save(@"D:\Tests\output.pdf");  
```

### See Also

* class [Page](../../../aspose.pdf/page)
* class [TextFragmentAbsorber](../../textfragmentabsorber)
* namespace [Aspose.Pdf.Text](../../textfragmentabsorber)
* assembly [Aspose.PDF](../../../)

---

## Visit(Document) {#visit}

Performs search on the specified document.

```csharp
public override void Visit(Document pdf)
```

| Parameter | Type | Description |
| --- | --- | --- |
| pdf | Document | PDF document object. |

### Examples

The example demonstrates how to find text on PDF document and replace text of all search occurrences.

```csharp
// Open document
Document doc = new Document(@"D:\Tests\input.pdf");

// Find font that will be used to change document text font
Aspose.Pdf.Txt.Font font = FontRepository.FindFont("Arial");

// Create TextFragmentAbsorber object to find all "hello world" text occurrences
TextFragmentAbsorber absorber = new TextFragmentAbsorber("hello world");

// Accept the absorber for first page
absorber.Visit(doc);

// Change text of the first text occurrence
absorber.TextFragments[1].Text = "hi world";

// Save document
doc.Save(@"D:\Tests\output.pdf");  
```

### See Also

* class [Document](../../../aspose.pdf/document)
* class [TextFragmentAbsorber](../../textfragmentabsorber)
* namespace [Aspose.Pdf.Text](../../textfragmentabsorber)
* assembly [Aspose.PDF](../../../)

---

## Visit(XForm) {#visit_2}

Performs search on the specified form object.

```csharp
public void Visit(XForm xForm)
```

| Parameter | Type | Description |
| --- | --- | --- |
| xForm | XForm | Pdf form object. |

### See Also

* class [XForm](../../../aspose.pdf/xform)
* class [TextFragmentAbsorber](../../textfragmentabsorber)
* namespace [Aspose.Pdf.Text](../../textfragmentabsorber)
* assembly [Aspose.PDF](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.PDF.dll -->
