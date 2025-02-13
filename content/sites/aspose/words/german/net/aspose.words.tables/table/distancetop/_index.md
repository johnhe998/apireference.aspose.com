---
title: Table.DistanceTop
second_title: Aspose.Words für .NET-API-Referenz
description: Table eigendom. Ruft den Abstand zwischen der Tischplatte und dem umgebenden Text in Punkten ab.
type: docs
weight: 150
url: /de/net/aspose.words.tables/table/distancetop/
---
## Table.DistanceTop property

Ruft den Abstand zwischen der Tischplatte und dem umgebenden Text in Punkten ab.

```csharp
public double DistanceTop { get; }
```

### Beispiele

Zeigt die Mindestabstandsoperationen zwischen Tabellengrenzen und Text an.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

Assert.AreEqual(25.9d, table.DistanceTop);
Assert.AreEqual(25.9d, table.DistanceBottom);
Assert.AreEqual(17.3d, table.DistanceLeft);
Assert.AreEqual(17.3d, table.DistanceRight);
```

### Siehe auch

* class [Table](../)
* namensraum [Aspose.Words.Tables](../../table/)
* Montage [Aspose.Words](../../../)


