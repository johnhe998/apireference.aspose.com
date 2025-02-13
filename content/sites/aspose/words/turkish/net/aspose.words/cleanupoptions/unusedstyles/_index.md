---
title: CleanupOptions.UnusedStyles
second_title: Aspose.Words for .NET API Referansı
description: CleanupOptions mülk. Kullanılmayan stillerin belgeden kaldırılması gerekip gerekmediğini belirtir. Varsayılan değer doğru .
type: docs
weight: 50
url: /tr/net/aspose.words/cleanupoptions/unusedstyles/
---
## CleanupOptions.UnusedStyles property

Kullanılmayan stillerin belgeden kaldırılması gerekip gerekmediğini belirtir. Varsayılan değer **doğru** .

```csharp
public bool UnusedStyles { get; set; }
```

### Örnekler

Bir belgeden kullanılmayan tüm özel stillerin nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// Yerleşik stiller ile birlikte, belgenin artık sekiz stili var.
// Belge içinde herhangi bir metin varken özel bir stil "kullanılmış" olarak işaretlenir
// bu tarzda biçimlendirilmiş. Bu, eklediğimiz 4 stilin şu anda kullanılmadığı anlamına gelir.
Assert.AreEqual(8, doc.Styles.Count);

// Özel bir karakter stili ve ardından özel bir liste stili uygulayın. Bunu yapmak onları "kullanılmış" olarak işaretleyecektir.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

// Şimdi, bir adet kullanılmayan karakter stili ve bir adet kullanılmayan liste stili var.
// Cleanup() yöntemi, bir CleanupOptions nesnesiyle yapılandırıldığında, kullanılmayan stilleri hedefleyebilir ve bunları kaldırabilir.
CleanupOptions cleanupOptions = new CleanupOptions
{
    UnusedLists = true, UnusedStyles = true, UnusedBuiltinStyles = true
};

doc.Cleanup(cleanupOptions);

Assert.AreEqual(4, doc.Styles.Count);

// Özel bir stilin uygulandığı her düğümü kaldırarak onu tekrar "kullanılmayan" olarak işaretlemek. 
// Bunları kaldırmak için Temizleme yöntemini yeniden çalıştırın.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup(cleanupOptions);

Assert.AreEqual(2, doc.Styles.Count);
```

### Ayrıca bakınız

* class [CleanupOptions](../)
* ad alanı [Aspose.Words](../../cleanupoptions/)
* toplantı [Aspose.Words](../../../)


