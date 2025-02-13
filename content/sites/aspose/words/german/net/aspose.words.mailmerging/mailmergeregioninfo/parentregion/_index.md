---
title: MailMergeRegionInfo.ParentRegion
second_title: Aspose.Words für .NET-API-Referenz
description: MailMergeRegionInfo eigendom. Gibt Informationen zur übergeordneten Region zurück null für die Region der obersten Ebene.
type: docs
weight: 50
url: /de/net/aspose.words.mailmerging/mailmergeregioninfo/parentregion/
---
## MailMergeRegionInfo.ParentRegion property

Gibt Informationen zur übergeordneten Region zurück (null für die Region der obersten Ebene).

```csharp
public MailMergeRegionInfo ParentRegion { get; }
```

### Beispiele

Zeigt, wie Seriendruckbereiche erstellt, aufgelistet und gelesen werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "TableStart"- und "TableEnd"-Tags, die in MERGEFIELDs gehen,
// die Zeichenfolgen bezeichnen, die den Beginn und das Ende von Seriendruckbereichen kennzeichnen.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// Verwenden Sie diese Tags, um eine Serienbriefregion mit dem Namen "MailMergeRegion1" zu starten und zu beenden,
// die MERGEFIELDs für zwei Spalten enthalten wird.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Wir können Zusammenführungsregionen und ihre Spalten verfolgen, indem wir uns diese Sammlungen ansehen.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// Füge eine Region mit demselben Namen in die bestehende Region ein, wodurch sie zu einer übergeordneten Region wird.
// Jetzt befindet sich ein "Column2"-Feld in einer neuen Region.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Wenn wir den Namen doppelter Regionen mit der Methode "GetRegionsByName" nachschlagen,
// Es werden alle diese Regionen in einer Sammlung zurückgegeben.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// Überprüfen Sie, ob die zweite Region jetzt eine übergeordnete Region hat.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### Siehe auch

* class [MailMergeRegionInfo](../)
* namensraum [Aspose.Words.MailMerging](../../mailmergeregioninfo/)
* Montage [Aspose.Words](../../../)


