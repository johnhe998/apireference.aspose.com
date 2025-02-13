---
title: StructuredDocumentTag.Id
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag mülk. Bunun için benzersiz bir salt okunur kalıcı sayısal kimlik belirtir SDT.
type: docs
weight: 140
url: /tr/net/aspose.words.markup/structureddocumenttag/id/
---
## StructuredDocumentTag.Id property

Bunun için benzersiz bir salt okunur kalıcı sayısal kimlik belirtir **SDT**.

```csharp
public int Id { get; }
```

### Notlar

Kimlik özelliği şu kurallara uyacaktır:

* Belge, yalnızca tüm belge klonlanmışsa SDT kimliklerini tutacaktır.[`Clone`](../../../aspose.words/document/clone/).
* Sırasında[`ImportNode`](../../../aspose.words/documentbase/importnode/) Id, içe aktarma hedef belgedeki içindeki diğer SDT Kimlikleri ile çakışmaya neden olmazsa saklanacaktır.
* Birden fazla SDT düğümü, Id özelliği, için aynı ondalık sayı değerini belirtirse, o zaman belgedeki ilk SDT, bu orijinal Id, 'yi koruyacak ve sonraki tüm SDT düğümlerinin, belge yüklendiğinde kendilerine atanan yeni tanımlayıcıları olacaktır.
* Bağımsız SDT sırasındaINodeCloningListener) işlemi, klonlanmış SDT düğümü için yeni benzersiz kimlik oluşturulacaktır.
* Kaynak belgede kimlik belirtilmemişse, belge yüklendiğinde SDT düğümüne yeni bir benzersiz tanımlayıcı atanmış olacaktır.

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


