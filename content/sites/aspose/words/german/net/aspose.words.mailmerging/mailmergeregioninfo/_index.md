---
title: Class MailMergeRegionInfo
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.MailMerging.MailMergeRegionInfo klas. Enthält Informationen zu einer Seriendruckregion.
type: docs
weight: 3640
url: /de/net/aspose.words.mailmerging/mailmergeregioninfo/
---
## MailMergeRegionInfo class

Enthält Informationen zu einer Seriendruckregion.

```csharp
public class MailMergeRegionInfo
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [EndField](../../aspose.words.mailmerging/mailmergeregioninfo/endfield/) { get; } | Gibt ein Endfeld für die Region zurück. |
| [Fields](../../aspose.words.mailmerging/mailmergeregioninfo/fields/) { get; } | Gibt eine Liste mit untergeordneten Feldern zurück. |
| [Level](../../aspose.words.mailmerging/mailmergeregioninfo/level/) { get; } | Gibt die Verschachtelungsebene für die Region zurück. |
| [Name](../../aspose.words.mailmerging/mailmergeregioninfo/name/) { get; } | Gibt den Namen der Region zurück. |
| [ParentRegion](../../aspose.words.mailmerging/mailmergeregioninfo/parentregion/) { get; } | Gibt Informationen zur übergeordneten Region zurück (null für die Region der obersten Ebene). |
| [Regions](../../aspose.words.mailmerging/mailmergeregioninfo/regions/) { get; } | Gibt eine Liste der untergeordneten Regionen zurück. |
| [StartField](../../aspose.words.mailmerging/mailmergeregioninfo/startfield/) { get; } | Gibt ein Startfeld für die Region zurück. |

### Beispiele

Zeigt, wie Seriendruckregionen überprüft werden.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Gibt eine vollständige Hierarchie von Zusammenführungsbereichen zurück, die MERGEFIELDs enthalten, die im Dokument verfügbar sind.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Obere Regionen im Dokument abrufen.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Holen Sie sich eine verschachtelte Region in der ersten oberen Region.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Liste der Felder innerhalb der ersten oberen Region abrufen.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Siehe auch

* namensraum [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* Montage [Aspose.Words](../../)


