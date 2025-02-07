---
title: CellFormat.ClearFormatting
second_title: Aspose.Words for .NET API Referansı
description: CellFormat yöntem. Varsayılan hücre biçimlendirmesine sıfırlar. Hücrenin genişliğini değiştirmez.
type: docs
weight: 150
url: /tr/net/aspose.words.tables/cellformat/clearformatting/
---
## CellFormat.ClearFormatting method

Varsayılan hücre biçimlendirmesine sıfırlar. Hücrenin genişliğini değiştirmez.

```csharp
public void ClearFormatting()
```

### Örnekler

İki tablodaki satırların tek bir tabloda nasıl birleştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Aşağıda bir belgeden tablo almanın iki yolu vardır.
// 1 - Bir Gövde düğümünün "Tablolar" koleksiyonundan:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - "GetChild" yöntemini kullanarak:
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Geçerli tablodaki tüm satırları bir sonrakine ekleyin.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Boş tablo kapsayıcısını kaldırın.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Ayrıca bakınız

* class [CellFormat](../)
* ad alanı [Aspose.Words.Tables](../../cellformat/)
* toplantı [Aspose.Words](../../../)


