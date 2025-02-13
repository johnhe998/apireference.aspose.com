---
title: MailMergeRegionInfo.EndField
second_title: Справочник по API Aspose.Words для .NET
description: MailMergeRegionInfo свойство. Возвращает конечное поле для региона.
type: docs
weight: 10
url: /ru/net/aspose.words.mailmerging/mailmergeregioninfo/endfield/
---
## MailMergeRegionInfo.EndField property

Возвращает конечное поле для региона.

```csharp
public FieldMergeField EndField { get; }
```

### Примеры

Показывает, как проверить регионы слияния.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Возвращает полную иерархию областей слияния, содержащих поля MERGEFIELD, доступные в документе.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Получить верхние регионы в документе.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Получить вложенную область в первой верхней области.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Получить список полей внутри первой верхней области.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Смотрите также

* class [FieldMergeField](../../../aspose.words.fields/fieldmergefield/)
* class [MailMergeRegionInfo](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmergeregioninfo/)
* сборка [Aspose.Words](../../../)


