---
title: FieldListNum.ListName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldListNum eigendom. Ruft den Namen der abstrakten Nummerierungsdefinition ab die für die Nummerierung verwendet wird oder legt ihn fest.
type: docs
weight: 40
url: /de/net/aspose.words.fields/fieldlistnum/listname/
---
## FieldListNum.ListName property

Ruft den Namen der abstrakten Nummerierungsdefinition ab, die für die Nummerierung verwendet wird, oder legt ihn fest.

```csharp
public string ListName { get; set; }
```

### Beispiele

Zeigt, wie Absätze mit LISTNUM-Feldern nummeriert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// LISTNUM-Felder zeigen eine Zahl an, die sich bei jedem LISTNUM-Feld erhöht.
// Diese Felder haben auch eine Vielzahl von Optionen, die es uns ermöglichen, sie zu verwenden, um nummerierte Listen zu emulieren.
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// Listen beginnen standardmäßig bei 1 zu zählen, aber wir können diese Zahl auf einen anderen Wert setzen, z. B. 0.
// Dieses Feld zeigt "0)" an.
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

 // LISTNUM-Felder verwalten separate Zählungen für jede Listenebene.
// Einfügen eines LISTNUM-Feldes in denselben Absatz wie ein anderes LISTNUM-Feld
// erhöht die Listenebene statt der Anzahl.
// Das nächste Feld setzt die oben begonnene Zählung fort und zeigt auf Listenebene 1 den Wert "1" an.
builder.InsertField(FieldType.FieldListNum, true);

// Dieses Feld startet eine Zählung auf Listenebene 2. Es zeigt den Wert "1" an.
builder.InsertField(FieldType.FieldListNum, true);

// Dieses Feld startet eine Zählung auf Listenebene 3. Es zeigt den Wert "1" an.
// Unterschiedliche Listenebenen haben unterschiedliche Formatierungen,
// so dass diese Felder zusammen einen Wert von "1)a)i)" anzeigen.
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// Das nächste LISTNUM-Feld, das wir einfügen, setzt die Zählung auf Listenebene fort
// dass das vorherige LISTNUM-Feld eingeschaltet war.
// Wir können die Eigenschaft "ListLevel" verwenden, um zu einer anderen Listenebene zu springen.
// Wenn dieses LISTNUM-Feld auf Listenebene 3 bleiben würde, würde es "ii)" anzeigen,
// aber da wir es auf Listenebene 2 verschoben haben, setzt es die Zählung auf dieser Ebene fort und zeigt "b)" an.
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// Wir können die ListName-Eigenschaft setzen, damit das Feld einen anderen AUTONUM-Feldtyp emuliert.
// "NumberDefault" emuliert AUTONUM, "OutlineDefault" emuliert AUTONUMOUT,
// und "LegalDefault" emuliert AUTONUMLGL-Felder.
// Der Listenname "OutlineDefault" mit 1 als Startnummer führt zur Anzeige von "I.".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// Der Listenname wird nicht aus dem vorherigen Feld übernommen, daher müssen wir ihn für jedes neue Feld festlegen.
// Dieses Feld setzt die Zählung mit dem anderen Listennamen fort und zeigt "II." an.
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### Siehe auch

* class [FieldListNum](../)
* namensraum [Aspose.Words.Fields](../../fieldlistnum/)
* Montage [Aspose.Words](../../../)


