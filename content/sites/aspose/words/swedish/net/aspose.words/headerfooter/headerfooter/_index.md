---
title: HeaderFooter.HeaderFooter
second_title: Aspose.Words för .NET API Referens
description: HeaderFooter byggare. Skapar en ny sidhuvud eller sidfot av den angivna typen.
type: docs
weight: 10
url: /sv/net/aspose.words/headerfooter/headerfooter/
---
## HeaderFooter constructor

Skapar en ny sidhuvud eller sidfot av den angivna typen.

```csharp
public HeaderFooter(DocumentBase doc, HeaderFooterType headerFooterType)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| doc | DocumentBase | Ägardokumentet. |
| headerFooterType | HeaderFooterType | A[`HeaderFooterType`](../headerfootertype/)värde som anger typen av sidhuvud eller sidfot. |

### Anmärkningar

När **Sidhuvud** skapas, det tillhör det angivna dokumentet, men är inte ännu en del av dokumentet och **ParentNode** är inget.

Att lägga till **Sidhuvud** till a **Sektion** använd Section.InsertAfter, Section.InsertBefore, HeadersFooters.Add eller HeadersFooters.Insert.

### Exempel

Visar hur man skapar ett sidhuvud och en sidfot.

```csharp
Document doc = new Document();

// Skapa en rubrik och lägg till ett stycke till den. Texten i det stycket
// kommer att visas överst på varje sida i det här avsnittet, ovanför huvudtexten.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// Skapa en sidfot och lägg till ett stycke till den. Texten i det stycket
// kommer att visas längst ned på varje sida i det här avsnittet, under huvudtexten.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### Se även

* class [DocumentBase](../../documentbase/)
* enum [HeaderFooterType](../../headerfootertype/)
* class [HeaderFooter](../)
* namnutrymme [Aspose.Words](../../headerfooter/)
* hopsättning [Aspose.Words](../../../)


