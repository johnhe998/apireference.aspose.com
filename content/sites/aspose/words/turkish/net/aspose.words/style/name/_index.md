---
title: Style.Name
second_title: Aspose.Words for .NET API Referansı
description: Style mülk. Stilin adını alır veya ayarlar.
type: docs
weight: 110
url: /tr/net/aspose.words/style/name/
---
## Style.Name property

Stilin adını alır veya ayarlar.

```csharp
public string Name { get; set; }
```

### Notlar

Boş dize olamaz.

Koleksiyonda zaten böyle bir ada sahip bir stil varsa, bu stil onu geçersiz kılar. Etkilenen tüm düğümler yeni stile başvuracaktır.

### Örnekler

Bir belgenin stil koleksiyonuna nasıl erişileceğini gösterir.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Aspose.Words kullanılarak oluşturulan bir belgenin varsayılan olarak içerdiği tüm stilleri numaralandırın ve listeleyin.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
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

* class [Style](../)
* ad alanı [Aspose.Words](../../style/)
* toplantı [Aspose.Words](../../../)


