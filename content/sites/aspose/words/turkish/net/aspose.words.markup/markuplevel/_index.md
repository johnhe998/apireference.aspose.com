---
title: Enum MarkupLevel
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Markup.MarkupLevel Sıralama. Belirli bir öğenin bulunduğu belge ağacındaki düzeyi belirtir.StructuredDocumentTag oluşabilir.
type: docs
weight: 3740
url: /tr/net/aspose.words.markup/markuplevel/
---
## MarkupLevel enumeration

Belirli bir öğenin bulunduğu belge ağacındaki düzeyi belirtir.[`StructuredDocumentTag`](../structureddocumenttag/) oluşabilir.

```csharp
public enum MarkupLevel
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Unknown | `0` | Bilinmeyen veya geçersiz değeri belirtir. |
| Inline | `1` | Öğe satır içi düzeyde gerçekleşir (örneğin metin dizileri arasında). |
| Block | `2` | Öğe, blok düzeyinde oluşur (örneğin tablolar ve paragraflar arasında). |
| Row | `3` | Öğe, bir tablodaki satırlar arasında yer alır. |
| Cell | `4` | Öğe, bir satırdaki hücreler arasında oluşur. |

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

* ad alanı [Aspose.Words.Markup](../../aspose.words.markup/)
* toplantı [Aspose.Words](../../)


