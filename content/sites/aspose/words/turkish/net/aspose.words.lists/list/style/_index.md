---
title: List.Style
second_title: Aspose.Words for .NET API Referansı
description: List mülk. Bu listenin başvurduğu veya tanımladığı liste stilini alır.
type: docs
weight: 80
url: /tr/net/aspose.words.lists/list/style/
---
## List.Style property

Bu listenin başvurduğu veya tanımladığı liste stilini alır.

```csharp
public Style Style { get; }
```

### Notlar

Bu liste bir liste stiliyle ilişkili değilse, özellik null değerini döndürür.

Bu durumda bir liste, bir liste stiline referans olabilir.[`IsListStyleReference`](../isliststylereference/) doğru olacak.

Bu durumda bir liste, bir liste stilinin tanımı olabilir.[`IsListStyleDefinition`](../isliststyledefinition/) doğru olacak. Böyle bir liste, belgedeki paragraflara doğrudan uygulanamaz.

### Örnekler

Liste stilinin nasıl oluşturulacağını ve bir belgede nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

// Liste, önek sembolleri ve girintilerle paragraf kümelerini düzenlememize ve süslememize olanak tanır.
// Girinti seviyesini artırarak iç içe listeler oluşturabiliriz. 
// Bir belge oluşturucunun "ListFormat" özelliğini kullanarak bir listeyi başlatabilir ve bitirebiliriz. 
// Bir listenin başlangıcı ile bitişi arasına eklediğimiz her paragraf listede bir öğe haline gelecektir.
// Bir stil içinde bir List nesnesinin tamamını içerebiliriz.
Style listStyle = doc.Styles.Add(StyleType.List, "MyListStyle");

List list1 = listStyle.List;

Assert.True(list1.IsListStyleDefinition);
Assert.False(list1.IsListStyleReference);
Assert.True(list1.IsMultiLevel);
Assert.AreEqual(listStyle, list1.Style);

// Listemizdeki tüm liste seviyelerinin görünümünü değiştirin.
foreach (ListLevel level in list1.ListLevels)
{
    level.Font.Name = "Verdana";
    level.Font.Color = Color.Blue;
    level.Font.Bold = true;
}

DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Using list style first time:");

// Bir stil içindeki bir listeden başka bir liste oluşturun.
List list2 = doc.Lists.Add(listStyle);

Assert.False(list2.IsListStyleDefinition);
Assert.True(list2.IsListStyleReference);
Assert.AreEqual(listStyle, list2.Style);

// Listemizin biçimlendireceği bazı liste öğelerini ekleyin.
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Writeln("Using list style second time:");

// Liste stiline göre başka bir liste oluşturun ve uygulayın.
List list3 = doc.Lists.Add(listStyle);
builder.ListFormat.List = list3;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateAndUseListStyle.docx");
```

### Ayrıca bakınız

* class [Style](../../../aspose.words/style/)
* class [List](../)
* ad alanı [Aspose.Words.Lists](../../list/)
* toplantı [Aspose.Words](../../../)


