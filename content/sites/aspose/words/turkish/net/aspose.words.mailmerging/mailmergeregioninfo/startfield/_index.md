---
title: MailMergeRegionInfo.StartField
second_title: Aspose.Words for .NET API Referansı
description: MailMergeRegionInfo mülk. Bölge için bir başlangıç alanı döndürür.
type: docs
weight: 70
url: /tr/net/aspose.words.mailmerging/mailmergeregioninfo/startfield/
---
## MailMergeRegionInfo.StartField property

Bölge için bir başlangıç alanı döndürür.

```csharp
public FieldMergeField StartField { get; }
```

### Örnekler

Adres mektup birleştirme bölgelerinin nasıl doğrulanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Belgede bulunan MERGEFIELD'leri içeren birleştirme bölgelerinin tam hiyerarşisini döndürür.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Belgedeki en iyi bölgeleri alın.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// İlk üst bölgede iç içe bölgeyi alın.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// İlk üst bölge içindeki alanların listesini alın.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Ayrıca bakınız

* class [FieldMergeField](../../../aspose.words.fields/fieldmergefield/)
* class [MailMergeRegionInfo](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmergeregioninfo/)
* toplantı [Aspose.Words](../../../)


