---
title: Class MailMergeRegionInfo
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.MailMerging.MailMergeRegionInfo klass. Innehåller information om en kopplingsregion.
type: docs
weight: 3640
url: /sv/net/aspose.words.mailmerging/mailmergeregioninfo/
---
## MailMergeRegionInfo class

Innehåller information om en kopplingsregion.

```csharp
public class MailMergeRegionInfo
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [EndField](../../aspose.words.mailmerging/mailmergeregioninfo/endfield/) { get; } | Returnerar ett slutfält för regionen. |
| [Fields](../../aspose.words.mailmerging/mailmergeregioninfo/fields/) { get; } | Returnerar en lista med underordnade fält. |
| [Level](../../aspose.words.mailmerging/mailmergeregioninfo/level/) { get; } | Returnerar kapslingsnivån för regionen. |
| [Name](../../aspose.words.mailmerging/mailmergeregioninfo/name/) { get; } | Returnerar namnet på regionen. |
| [ParentRegion](../../aspose.words.mailmerging/mailmergeregioninfo/parentregion/) { get; } | Returnerar information om överordnad region (null för region på toppnivå). |
| [Regions](../../aspose.words.mailmerging/mailmergeregioninfo/regions/) { get; } | Returnerar en lista över underordnade regioner. |
| [StartField](../../aspose.words.mailmerging/mailmergeregioninfo/startfield/) { get; } | Returnerar ett startfält för regionen. |

### Exempel

Visar hur man verifierar kopplingsregioner.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Returnerar en fullständig hierarki av sammanslagningsregioner som innehåller MERGEFIELDs tillgängliga i dokumentet.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Få toppregioner i dokumentet.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Få kapslad region i första toppregionen.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Hämta lista över fält inom den första toppregionen.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Se även

* namnutrymme [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* hopsättning [Aspose.Words](../../)


