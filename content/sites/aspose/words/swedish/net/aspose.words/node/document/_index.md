---
title: Node.Document
second_title: Aspose.Words för .NET API Referens
description: Node fast egendom. Hämtar dokumentet som denna nod tillhör.
type: docs
weight: 20
url: /sv/net/aspose.words/node/document/
---
## Node.Document property

Hämtar dokumentet som denna nod tillhör.

```csharp
public virtual DocumentBase Document { get; }
```

### Anmärkningar

Noden tillhör alltid ett dokument även om den precis har skapats och ännu inte lagts till i trädet, eller om den har tagits bort från trädet.

### Exempel

Visar hur man skapar en nod och ställer in dess ägande dokument.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
para.AppendChild(new Run(doc, "Hello world!"));

// Vi har ännu inte lagt till detta stycke som ett underordnat till någon sammansatt nod.
Assert.IsNull(para.ParentNode);

// Om en nod är en lämplig undernodstyp till en annan sammansatt nod,
// vi kan bifoga det som ett barn endast om båda noderna har samma ägardokument.
// Ägardokumentet är dokumentet vi skickade till nodens konstruktor.
// Vi har inte bifogat denna paragraf till dokumentet, så dokumentet innehåller inte dess text.
Assert.AreEqual(para.Document, doc);
Assert.AreEqual(string.Empty, doc.GetText().Trim());

// Eftersom dokumentet äger detta stycke kan vi tillämpa en av dess stilar på styckets innehåll.
para.ParagraphFormat.Style = doc.Styles["Heading 1"];

// Lägg till denna nod i dokumentet och verifiera sedan dess innehåll.
doc.FirstSection.Body.AppendChild(para);

Assert.AreEqual(doc.FirstSection.Body, para.ParentNode);
Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Se även

* class [DocumentBase](../../documentbase/)
* class [Node](../)
* namnutrymme [Aspose.Words](../../node/)
* hopsättning [Aspose.Words](../../../)


