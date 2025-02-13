---
title: StructuredDocumentTag.StyleName
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag mülk. Yapılandırılmış belge etiketine uygulanan stilin adını alır veya ayarlar.
type: docs
weight: 270
url: /tr/net/aspose.words.markup/structureddocumenttag/stylename/
---
## StructuredDocumentTag.StyleName property

Yapılandırılmış belge etiketine uygulanan stilin adını alır veya ayarlar.

```csharp
public string StyleName { get; set; }
```

### Örnekler

İçerik kontrol öğeleri için stiller ile nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aşağıda, belgeden yapılandırılmış bir belge etiketine bir stil uygulamanın iki yolu verilmiştir.
// 1 - Belgenin stil koleksiyonundan bir stil nesnesi uygulayın:
Style quoteStyle = doc.Styles[StyleIdentifier.Quote];
StructuredDocumentTag sdtPlainText =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline) { Style = quoteStyle };

// 2 - Belgedeki bir stile ada göre başvuru yapın:
StructuredDocumentTag sdtRichText =
    new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Inline) { StyleName = "Quote" };

builder.InsertNode(sdtPlainText);
builder.InsertNode(sdtRichText);

Assert.AreEqual(NodeType.StructuredDocumentTag, sdtPlainText.NodeType);

NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true);

foreach (Node node in tags)
{
    StructuredDocumentTag sdt = (StructuredDocumentTag)node;

    Assert.AreEqual(StyleIdentifier.Quote, sdt.Style.StyleIdentifier);
    Assert.AreEqual("Quote", sdt.StyleName);
}
```

### Ayrıca bakınız

* class [StructuredDocumentTag](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttag/)
* toplantı [Aspose.Words](../../../)


