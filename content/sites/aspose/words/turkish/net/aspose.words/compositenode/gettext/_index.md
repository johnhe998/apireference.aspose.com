---
title: CompositeNode.GetText
second_title: Aspose.Words for .NET API Referansı
description: CompositeNode yöntem. Bu düğümün ve tüm alt öğelerinin metnini alır.
type: docs
weight: 120
url: /tr/net/aspose.words/compositenode/gettext/
---
## CompositeNode.GetText method

Bu düğümün ve tüm alt öğelerinin metnini alır.

```csharp
public override string GetText()
```

### Notlar

Döndürülen dize, içinde açıklandığı gibi tüm kontrol ve özel karakterleri içerir.[`ControlChar`](../../controlchar/).

### Örnekler

Bir düğümde GetText ve ToString yöntemlerini çağırma arasındaki farkı gösterir.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("MERGEFIELD Field");

// GetText görünen metni, alan kodlarını ve özel karakterleri alacaktır.
Assert.AreEqual("\u0013MERGEFIELD Field\u0014«Field»\u0015\u000c", doc.GetText());

// ToString, geçmiş bir kaydetme biçimine kaydedilirse bize belgenin görünümünü verir.
Assert.AreEqual("«Field»\r\n", doc.ToString(SaveFormat.Text));
```

Liste öğeleri olan bir belgedeki tüm paragrafların nasıl çıktısının alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Numbered list item 1");
builder.Writeln("Numbered list item 2");
builder.Writeln("Numbered list item 3");
builder.ListFormat.RemoveNumbers();

builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Bulleted list item 1");
builder.Writeln("Bulleted list item 2");
builder.Writeln("Bulleted list item 3");
builder.ListFormat.RemoveNumbers();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{ 
    Console.WriteLine($"This paragraph belongs to list ID# {para.ListFormat.List.ListId}, number style \"{para.ListFormat.ListLevel.NumberStyle}\"");
    Console.WriteLine($"\t\"{para.GetText().Trim()}\"");
}
```

### Ayrıca bakınız

* class [CompositeNode](../)
* ad alanı [Aspose.Words](../../compositenode/)
* toplantı [Aspose.Words](../../../)


