---
title: FieldAddressBlock.GetFieldNames
second_title: Aspose.Words for .NET API Referansı
description: FieldAddressBlock yöntem. Alan tarafından kullanılan adres mektup birleştirme alan adlarının bir koleksiyonunu döndürür.
type: docs
weight: 70
url: /tr/net/aspose.words.fields/fieldaddressblock/getfieldnames/
---
## FieldAddressBlock.GetFieldNames method

Alan tarafından kullanılan adres mektup birleştirme alan adlarının bir koleksiyonunu döndürür.

```csharp
public string[] GetFieldNames()
```

### Örnekler

Bir alan tarafından kullanılan adres mektup birleştirme alan adlarının nasıl alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Field sample - ADDRESSBLOCK.docx");

string[] addressFieldsExpect =
{
    "Company", "First Name", "Middle Name", "Last Name", "Suffix", "Address 1", "City", "State",
    "Country or Region", "Postal Code"
};

FieldAddressBlock addressBlockField = (FieldAddressBlock) doc.Range.Fields[0];
string[] addressBlockFieldNames = addressBlockField.GetFieldNames();
```

### Ayrıca bakınız

* class [FieldAddressBlock](../)
* ad alanı [Aspose.Words.Fields](../../fieldaddressblock/)
* toplantı [Aspose.Words](../../../)


