---
title: MailMerge.TrimWhitespaces
second_title: Aspose.Words för .NET API Referens
description: MailMerge fast egendom. Hämtar eller ställer in ett värde som anger om efterföljande och inledande blanksteg beskärs från sammanslagningsvärden.
type: docs
weight: 130
url: /sv/net/aspose.words.mailmerging/mailmerge/trimwhitespaces/
---
## MailMerge.TrimWhitespaces property

Hämtar eller ställer in ett värde som anger om efterföljande och inledande blanksteg beskärs från sammanslagningsvärden.

```csharp
public bool TrimWhitespaces { get; set; }
```

### Anmärkningar

Standardvärdet är **Sann** .

### Exempel

Visar hur man trimmar blanksteg från värden för en datakälla medan en e-postsammanslagning körs.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD myMergeField", null);

doc.MailMerge.TrimWhitespaces = trimWhitespaces;
doc.MailMerge.Execute(new[] { "myMergeField" }, new object[] { "\t hello world! " });

Assert.AreEqual(trimWhitespaces ? "hello world!\f" : "\t hello world! \f", doc.GetText());
```

### Se även

* class [MailMerge](../)
* namnutrymme [Aspose.Words.MailMerging](../../mailmerge/)
* hopsättning [Aspose.Words](../../../)


