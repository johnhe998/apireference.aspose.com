---
title: MailMerge.GetRegionsHierarchy
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge methode. Gibt eine vollständige Hierarchie von Regionen mit Feldern zurück die im Dokument verfügbar sind.
type: docs
weight: 250
url: /de/net/aspose.words.mailmerging/mailmerge/getregionshierarchy/
---
## MailMerge.GetRegionsHierarchy method

Gibt eine vollständige Hierarchie von Regionen (mit Feldern) zurück, die im Dokument verfügbar sind.

```csharp
public MailMergeRegionInfo GetRegionsHierarchy()
```

### Rückgabewert

Hierarchie der Regionen.

### Bemerkungen

Die Hierarchie wird in Form von zurückgegeben[`MailMergeRegionInfo`](../../mailmergeregioninfo/) Klasse.

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

* class [MailMergeRegionInfo](../../mailmergeregioninfo/)
* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


