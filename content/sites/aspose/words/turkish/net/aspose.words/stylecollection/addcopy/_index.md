---
title: StyleCollection.AddCopy
second_title: Aspose.Words for .NET API Referansı
description: StyleCollection yöntem. Bu koleksiyona bir stil kopyalar.
type: docs
weight: 70
url: /tr/net/aspose.words/stylecollection/addcopy/
---
## StyleCollection.AddCopy method

Bu koleksiyona bir stil kopyalar.

```csharp
public Style AddCopy(Style style)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| style | Style | Kopyalanacak stil. |

### Geri dönüş değeri

Kopyalanmış stil kullanıma hazır.

### Notlar

Kopyalanacak stil aynı belgeye ait olabileceği gibi farklı bir belgeye de ait olabilir.

Bağlantılı stil kopyalanır.

Bu yöntem, temel stilleri kopyalamaz.

Koleksiyon zaten aynı ada sahip bir stil içeriyorsa, yeni ad is 0'dan başlayarak "_number" eki eklenerek otomatik olarak oluşturulur, örneğin "Normal_0", "Heading 1_1" vb. Kullan[`Name`](../../style/name/) içe aktarılan stilin adını değiştirmek için ayarlayıcı.

### Örnekler

Bir stilin bir belgeden farklı bir belgeye nasıl içe aktarılacağını gösterir.

```csharp
Document srcDoc = new Document();

// Kaynak belge için özel bir stil oluşturun.
Style srcStyle = srcDoc.Styles.Add(StyleType.Paragraph, "MyStyle");
srcStyle.Font.Color = Color.Red;

// Kaynak belgenin özel stilini hedef belgeye aktarın.
Document dstDoc = new Document();
Style newStyle = dstDoc.Styles.AddCopy(srcStyle);

// İçe aktarılan stil, kaynak stiliyle aynı görünüme sahiptir.
Assert.AreEqual("MyStyle", newStyle.Name);
Assert.AreEqual(Color.Red.ToArgb(), newStyle.Font.Color.ToArgb());
```

Bir belgenin stilinin nasıl klonlanacağını gösterir.

```csharp
Document doc = new Document();

// AddCopy yöntemi, belirtilen stilin bir kopyasını oluşturur ve
// stil için otomatik olarak "Heading 1_0" gibi yeni bir ad oluşturur.
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// Stilin tanımlayıcı adını değiştirmek için stilin "Ad" özelliğini kullanın.
newStyle.Name = "My Heading 1";

// Belgemiz artık farklı adlara sahip iki özdeş görünümlü stile sahip.
// Stillerden birinin ayarlarının değiştirilmesi diğerini etkilemez.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### Ayrıca bakınız

* class [Style](../../style/)
* class [StyleCollection](../)
* ad alanı [Aspose.Words](../../stylecollection/)
* toplantı [Aspose.Words](../../../)


