---
title: Class CustomDocumentProperties
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Properties.CustomDocumentProperties sınıf. Özel belge özellikleri koleksiyonu.
type: docs
weight: 4210
url: /tr/net/aspose.words.properties/customdocumentproperties/
---
## CustomDocumentProperties class

Özel belge özellikleri koleksiyonu.

```csharp
public class CustomDocumentProperties : DocumentPropertyCollection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words.properties/documentpropertycollection/count/) { get; } | Koleksiyondaki öğe sayısını alır. |
| [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Bir döndürür[`DocumentProperty`](../documentproperty/) dizine göre nesne. |
| virtual [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Bir döndürür[`DocumentProperty`](../documentproperty/) özelliğin adına göre nesne. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add)(string, bool) | Dosyanın yeni bir özel belge özelliğini oluşturur. **PropertyType.Boole** veri türü. |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_3)(string, DateTime) | Dosyanın yeni bir özel belge özelliğini oluşturur. **PropertyType.DateTime** veri türü. |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_1)(string, double) | Dosyanın yeni bir özel belge özelliğini oluşturur. **PropertyType.Float** veri türü. |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_2)(string, int) | Dosyanın yeni bir özel belge özelliğini oluşturur. **PropertyType.Number** veri türü. |
| [Add](../../aspose.words.properties/customdocumentproperties/add/#add_4)(string, string) | Dosyanın yeni bir özel belge özelliğini oluşturur. **PropertyType.String** veri türü. |
| [AddLinkToContent](../../aspose.words.properties/customdocumentproperties/addlinktocontent/)(string, string) | İçeriğe bağlı yeni bir özel belge özelliği oluşturur. |
| [Clear](../../aspose.words.properties/documentpropertycollection/clear/)() | Koleksiyondaki tüm özellikleri kaldırır. |
| [Contains](../../aspose.words.properties/documentpropertycollection/contains/)(string) | Koleksiyonda belirtilen ada sahip bir özellik varsa true değerini döndürür. |
| [GetEnumerator](../../aspose.words.properties/documentpropertycollection/getenumerator/)() | Koleksiyondaki tüm öğeler üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür. |
| [IndexOf](../../aspose.words.properties/documentpropertycollection/indexof/)(string) | Ada göre bir özelliğin dizinini alır. |
| [Remove](../../aspose.words.properties/documentpropertycollection/remove/)(string) | Belirtilen ada sahip bir özelliği koleksiyondan kaldırır. |
| [RemoveAt](../../aspose.words.properties/documentpropertycollection/removeat/)(int) | Belirtilen dizindeki bir özelliği kaldırır. |

### Notlar

Her biri[`DocumentProperty`](../documentproperty/) nesne, bir kapsayıcı belgesinin özel bir özelliğini temsil eder.

Özelliklerin adları büyük/küçük harfe duyarsızdır.

Koleksiyondaki özellikler ada göre alfabetik olarak sıralanır.

### Örnekler

Özel belge özellikleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Her belge, yerleşik özellikler gibi anahtar/değer çiftleri olan bir özel özellikler koleksiyonu içerir.
// Belgenin yerleşik özelliklerin sabit bir listesi vardır. Kullanıcı, tüm özel özellikleri oluşturur. 
Assert.AreEqual("Value of custom document property", doc.CustomDocumentProperties["CustomProperty"].ToString());

doc.CustomDocumentProperties.Add("CustomProperty2", "Value of custom document property #2");

Console.WriteLine("Custom Properties:");
foreach (var customDocumentProperty in doc.CustomDocumentProperties)
{
    Console.WriteLine(customDocumentProperty.Name);
    Console.WriteLine($"\tType:\t{customDocumentProperty.Type}");
    Console.WriteLine($"\tValue:\t\"{customDocumentProperty.Value}\"");
}
```

### Ayrıca bakınız

* class [Document](../../aspose.words/document/)
* property [BuiltInDocumentProperties](../../aspose.words/document/builtindocumentproperties/)
* property [CustomDocumentProperties](../../aspose.words/document/customdocumentproperties/)
* class [DocumentPropertyCollection](../documentpropertycollection/)
* ad alanı [Aspose.Words.Properties](../../aspose.words.properties/)
* toplantı [Aspose.Words](../../)


