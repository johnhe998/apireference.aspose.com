---
title: StructuredDocumentTag.RemoveSelfOnly
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag yöntem. Yalnızca bu SDT düğümünün kendisini kaldırır ancak içeriğini belge ağacının içinde tutar.
type: docs
weight: 340
url: /tr/net/aspose.words.markup/structureddocumenttag/removeselfonly/
---
## StructuredDocumentTag.RemoveSelfOnly method

Yalnızca bu SDT düğümünün kendisini kaldırır, ancak içeriğini belge ağacının içinde tutar.

```csharp
public void RemoveSelfOnly()
```

### Örnekler

Düz metin kutusunda yapılandırılmış bir belge etiketinin nasıl oluşturulacağını ve görünümünün nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();

// Düz metin içerecek yapılandırılmış bir belge etiketi oluşturun.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Microsoft Word'de yapılandırılmış belge etiketinin üzerine geldiğinizde görünen çerçevenin başlığını ve rengini ayarlayın.
tag.Title = "My plain text";
tag.Color = Color.Magenta;

// Bu yapılandırılmış belge etiketi için elde edilebilecek bir etiket ayarlayın
// "etiket" adlı bir XML öğesi olarak, "@val" özniteliğinde aşağıdaki dizeyle.
tag.Tag = "MyPlainTextSDT";

// Her yapılandırılmış belge etiketinin rastgele benzersiz bir kimliği vardır.
Assert.That(tag.Id, Is.Positive);

// Yapılandırılmış belge etiketi içindeki metnin yazı tipini ayarlayın.
tag.ContentsFont.Name = "Arial";

// Yapılandırılmış belge etiketinin sonundaki metin için yazı tipini ayarlayın.
// Ok tuşları ile etiketin dışına çıktıktan sonra belge gövdesine yazdığımız herhangi bir metin bu yazı tipini kullanacaktır.
tag.EndCharacterFont.Name = "Arial Black";

// Varsayılan olarak, bu yanlıştır ve yapılandırılmış bir belge etiketinin içindeyken enter tuşuna basmak hiçbir şey yapmaz.
// true olarak ayarlandığında, yapılandırılmış belge etiketimizin birden çok satırı olabilir.

// Yalnızca içeriğe izin vermek için "Multiline" özelliğini "false" olarak ayarlayın
// tek bir satıra yayılacak bu yapılandırılmış belge etiketinin.
// Etiketin birden çok içerik satırı içermesine izin vermek için "Multiline" özelliğini "true" olarak ayarlayın.
tag.Multiline = true;

// İçeriğin etrafındaki etiketleri göstermek için "Appearance" özelliğini "SdtAppearance.Tags" olarak ayarlayın.
 // Varsayılan olarak yapılandırılmış belge etiketi BoundingBox olarak gösterilir.
tag.Appearance = SdtAppearance.Tags;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

// Yapılandırılmış belge etiketimizin bir klonunu yeni bir paragrafa ekleyin.
StructuredDocumentTag tagClone = (StructuredDocumentTag)tag.Clone(true);
builder.InsertParagraph();
builder.InsertNode(tagClone);

// Yapılandırılmış bir belge etiketini, içeriğini belgede tutarken kaldırmak için "RemoveSelfOnly" yöntemini kullanın.
tagClone.RemoveSelfOnly();

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlainText.docx");
```

### Ayrıca bakınız

* class [StructuredDocumentTag](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttag/)
* toplantı [Aspose.Words](../../../)


