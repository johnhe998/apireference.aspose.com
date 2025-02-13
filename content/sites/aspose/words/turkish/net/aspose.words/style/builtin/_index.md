---
title: Style.BuiltIn
second_title: Aspose.Words for .NET API Referansı
description: Style mülk. Bu stil MS Worddeki yerleşik stillerden biriyse doğrudur.
type: docs
weight: 30
url: /tr/net/aspose.words/style/builtin/
---
## Style.BuiltIn property

Bu stil MS Word'deki yerleşik stillerden biriyse doğrudur.

```csharp
public bool BuiltIn { get; }
```

### Örnekler

Özel stilleri yerleşik stillerden nasıl ayırt edeceğinizi gösterir.

```csharp
Document doc = new Document();

// Microsoft Word kullanarak veya programlı olarak Aspose.Words kullanarak bir belge oluşturduğumuzda,
// belge, görünümünü değiştirmek için metnine uygulanacak bir stil koleksiyonuyla birlikte gelir.
// Bu yerleşik stillere belgenin "Stiller" koleksiyonu aracılığıyla erişebiliriz.
// Bu stillerin hepsinde "Yerleşik" bayrağı "true" olarak ayarlanacaktır.
Style style = doc.Styles["Emphasis"];

Assert.True(style.BuiltIn);

// Özel bir stil oluşturun ve koleksiyona ekleyin.
 // Bunun gibi özel stillerde "Yerleşik" bayrağı "yanlış" olarak ayarlanır.
style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Navy;
style.Font.Name = "Courier New";

Assert.False(style.BuiltIn);
```

### Ayrıca bakınız

* class [Style](../)
* ad alanı [Aspose.Words](../../style/)
* toplantı [Aspose.Words](../../../)


