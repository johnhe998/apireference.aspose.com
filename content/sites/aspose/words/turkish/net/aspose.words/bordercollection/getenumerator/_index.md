---
title: BorderCollection.GetEnumerator
second_title: Aspose.Words for .NET API Referansı
description: BorderCollection yöntem. Koleksiyondaki tüm kenarlıklar üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür.
type: docs
weight: 160
url: /tr/net/aspose.words/bordercollection/getenumerator/
---
## BorderCollection.GetEnumerator method

Koleksiyondaki tüm kenarlıklar üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür.

```csharp
public IEnumerator<Border> GetEnumerator()
```

### Örnekler

Paragraf biçimi nesnesindeki tüm sınırların nasıl yineleneceğini ve düzenleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Her tarafta yeşil bir dalga sınırı oluşturmak için oluşturucunun paragraf biçimi ayarlarını yapılandırın.
BorderCollection borders = builder.ParagraphFormat.Borders;

using (IEnumerator<Border> enumerator = borders.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Border border = enumerator.Current;
        border.Color = Color.Green;
        border.LineStyle = LineStyle.Wave;
        border.LineWidth = 3;
    }
}

// Paragraf ekle. Kenarlık ayarlarımız, kenarlığının görünümünü belirleyecektir.
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "BorderCollection.GetBordersEnumerator.docx");
```

### Ayrıca bakınız

* class [Border](../../border/)
* class [BorderCollection](../)
* ad alanı [Aspose.Words](../../bordercollection/)
* toplantı [Aspose.Words](../../../)


