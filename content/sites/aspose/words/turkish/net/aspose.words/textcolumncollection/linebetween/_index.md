---
title: TextColumnCollection.LineBetween
second_title: Aspose.Words for .NET API Referansı
description: TextColumnCollection mülk. Ne zaman doğru  sütunlar arasına dikey bir çizgi ekler.
type: docs
weight: 40
url: /tr/net/aspose.words/textcolumncollection/linebetween/
---
## TextColumnCollection.LineBetween property

Ne zaman **doğru** , sütunlar arasına dikey bir çizgi ekler.

```csharp
public bool LineBetween { get; set; }
```

### Örnekler

Sütunların dikey bir çizgiyle nasıl ayrılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Metni birkaç sütuna bölmek için geçerli bölümün PageSetup nesnesini yapılandırın.
// Sütunlar arasına bir bölme çizgisi koymak için "LineBetween" özelliğini "true" olarak ayarlayın.
// Sütunlar arasındaki boşluğu boş bırakmak için "LineBetween" özelliğini "false" olarak ayarlayın.
TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.LineBetween = lineBetween;
columns.SetCount(3);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 3.");

doc.Save(ArtifactsDir + "PageSetup.VerticalLineBetweenColumns.docx");
```

### Ayrıca bakınız

* class [TextColumnCollection](../)
* ad alanı [Aspose.Words](../../textcolumncollection/)
* toplantı [Aspose.Words](../../../)


