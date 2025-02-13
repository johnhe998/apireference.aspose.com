---
title: FieldIndex.RunSubentriesOnSameLine
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIndex eigendom. Ruft ab oder legt fest ob Untereinträge in derselben Zeile wie der Haupteintrag ausgeführt werden.
type: docs
weight: 140
url: /de/net/aspose.words.fields/fieldindex/runsubentriesonsameline/
---
## FieldIndex.RunSubentriesOnSameLine property

Ruft ab oder legt fest, ob Untereinträge in derselben Zeile wie der Haupteintrag ausgeführt werden.

```csharp
public bool RunSubentriesOnSameLine { get; set; }
```

### Beispiele

Zeigt, wie mit Untereinträgen in einem INDEX-Feld gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an,
// und die Nummer der Seite, die rechts das XE-Feld enthält.
// Der INDEX-Eintrag sammelt alle XE-Felder mit übereinstimmenden Werten in der Eigenschaft "Text".
// in einen Eintrag anstatt für jedes XE-Feld einen Eintrag zu machen.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.PageNumberSeparator = ", see page ";
index.Heading = "A";

// XE-Felder mit einer Text-Eigenschaft, deren Wert zur Überschrift des INDEX-Eintrags wird.
// Wenn dieser Wert zwei Stringsegmente enthält, die durch einen Doppelpunkt getrennt sind (der INDEX-Eintrag behandelt :) Trennzeichen,
// Das erste Segment ist die Überschrift und das zweite Segment wird zur Unterüberschrift.
// Das INDEX-Feld gruppiert Einträge zuerst alphabetisch, dann, wenn es mehrere XE-Felder gibt, mit denselben
// Überschriften, das INDEX-Feld wird sie weiter nach den Werten dieser Überschriften untergruppieren.
// Es kann mehrere Untergruppierungsebenen geben, je nachdem, wie oft
// die Texteigenschaften von XE-Feldern werden so segmentiert.
 // Standardmäßig erstellt eine INDEX-Feldeintragsgruppe eine neue Zeile für jede Unterüberschrift innerhalb dieser Gruppe.
// Wir können das Flag RunSubentriesOnSameLine auf true setzen, um die Überschrift beizubehalten,
// und jede Unterüberschrift für die Gruppe stattdessen in einer Zeile, wodurch das INDEX-Feld kompakter wird.
index.RunSubentriesOnSameLine = runSubentriesOnTheSameLine;

if (runSubentriesOnTheSameLine)
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A \\r", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A", index.GetFieldCode());

// Zwei XE-Felder einfügen, jedes auf einer neuen Seite und mit der gleichen Überschrift namens "Überschrift 1",
// die das INDEX-Feld verwendet, um sie zu gruppieren.
// Wenn RunSubentriesOnSameLine falsch ist, erstellt die INDEX-Tabelle drei Zeilen:
// eine Zeile für die Gruppierungsüberschrift „Überschrift 1“ und eine weitere Zeile für jede Unterüberschrift.
// Wenn RunSubentriesOnSameLine wahr ist, erstellt die INDEX-Tabelle eine Einzeile
// Eintrag, der die Überschrift und alle Unterüberschriften umfasst.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 1";

Assert.AreEqual(" XE  \"Heading 1:Subheading 1\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 2";

doc.UpdateFields();
doc.Save(ArtifactsDir + $"Field.INDEX.XE.Subheading.docx");
```

### Siehe auch

* class [FieldIndex](../)
* namensraum [Aspose.Words.Fields](../../fieldindex/)
* Montage [Aspose.Words](../../../)


