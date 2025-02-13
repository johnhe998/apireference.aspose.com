---
title: ParagraphFormat.Bidi
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Bunun sağdan sola bir paragraf olup olmadığını alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words/paragraphformat/bidi/
---
## ParagraphFormat.Bidi property

Bunun sağdan sola bir paragraf olup olmadığını alır veya ayarlar.

```csharp
public bool Bidi { get; set; }
```

### Notlar

Doğru olduğunda, bu paragraf içindeki çalıştırmalar ve diğer satır içi nesneler sağdan sola düzenlenir.

### Örnekler

Düz metin belgesi metin yönünün nasıl algılanacağını gösterir.

```csharp
// Bir belgenin yapıcısına iletebileceğimiz bir "TxtLoadOptions" nesnesi oluşturun
// bir düz metin belgesini nasıl yüklediğimizi değiştirmek için.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// "DocumentDirection" özelliğini "DocumentDirection.Auto" olarak ayarlayın, otomatik olarak algılar
// Aspose.Words'ün düz metinden yüklediği metnin her paragrafının yönü.
// Her paragrafın "Bidi" özelliği, yönünü saklayacaktır.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// İbranice metni sağdan sola olarak algıla.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// İngilizce metni sağdan sola olarak algıla.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

BIDIOUTLINE alanlarıyla sağdan sola dil uyumlu listelerin nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// BIDIOUTLINE alanı, AUTONUM/LISTNUM alanları gibi paragrafları numaralandırır,
// ancak yalnızca İbranice veya Arapça gibi bir sağdan sola düzenleme dili etkinleştirildiğinde görünür.
// Aşağıdaki alan, "1" liste numarasının RTL karşılığı olan ".1"i gösterecektir.
FieldBidiOutline field = (FieldBidiOutline)builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

Assert.AreEqual(" BIDIOUTLINE ", field.GetFieldCode());

// ".2" ve ".3" görüntüleyecek iki BIDIOUTLINE alanı daha ekleyin.
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

// Belgedeki her paragraf için yatay metin hizalamasını RTL'ye ayarlayın.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.Bidi = true;
}

// Microsoft Word'de sağdan sola düzenleme dilini etkinleştirirsek, alanlarımız sayıları görüntüler.
// Aksi takdirde, "###" gösterecektir.
doc.Save(ArtifactsDir + "Field.BIDIOUTLINE.docx");
```

### Ayrıca bakınız

* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


