---
title: FieldIndex.HasSequenceName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIndex eigendom. Ruft einen Wert ab der angibt ob bei der Ergebnisbildung des Felds eine Sequenz verwendet werden soll.
type: docs
weight: 60
url: /de/net/aspose.words.fields/fieldindex/hassequencename/
---
## FieldIndex.HasSequenceName property

Ruft einen Wert ab, der angibt, ob bei der Ergebnisbildung des Felds eine Sequenz verwendet werden soll.

```csharp
public bool HasSequenceName { get; }
```

### Beispiele

Zeigt, wie ein Dokument durch Kombinieren von INDEX- und SEQ-Feldern in Teile aufgeteilt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an,
// und die Nummer der Seite, die rechts das XE-Feld enthält.
// Wenn die XE-Felder den gleichen Wert in ihrer "Text"-Eigenschaft haben,
// das Feld INDEX gruppiert sie zu einem Eintrag.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Benennen Sie in der Eigenschaft SequenceName eine SEQ-Feldsequenz. Jeder Eintrag dieses INDEX-Feldes wird nun ebenfalls angezeigt
// die Nummer, auf der sich der Sequenzzähler an der XE-Feldposition befindet, die diesen Eintrag erstellt hat.
index.SequenceName = "MySequence";

// Legen Sie Text fest, der die Sequenz- und Seitenzahlen umgibt, um dem Benutzer ihre Bedeutung zu erklären.
// Ein mit dieser Konfiguration erstellter Eintrag zeigt so etwas wie "MySequence at 1 on page 1" an seiner Seitennummer an.
// PageNumberSeparator und SequenceSeparator dürfen nicht länger als 15 Zeichen sein.
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// SEQ-Felder zeigen einen Zähler an, der sich bei jedem SEQ-Feld erhöht.
// Diese Felder verwalten auch separate Zählwerte für jede eindeutig benannte Sequenz
// identifiziert durch die "SequenceIdentifier"-Eigenschaft des SEQ-Felds.
// Füge ein SEQ-Feld ein, das die "MySequence"-Sequenz auf 1 verschiebt.
// Dieses Feld unterscheidet sich nicht vom normalen Dokumenttext. Es erscheint nicht im Inhaltsverzeichnis eines INDEX-Feldes.
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// Fügen Sie ein XE-Feld ein, das einen Eintrag im INDEX-Feld erstellt.
// Da "MySequence" auf 1 steht und dieses XE-Feld auf Seite 2 ist, zusammen mit den benutzerdefinierten Trennzeichen, die wir oben definiert haben,
// Der INDEX-Eintrag dieses Felds zeigt "Cat" auf der linken Seite und "MySequence at 1 on page 2" auf der rechten Seite an.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// Einen Seitenumbruch einfügen und SEQ-Felder verwenden, um "MySequence" auf 3 zu bringen.
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// Fügen Sie ein XE-Feld mit derselben Text-Eigenschaft wie oben ein.
// Der INDEX-Eintrag gruppiert XE-Felder mit übereinstimmenden Werten in der Eigenschaft "Text".
// in einen Eintrag anstatt für jedes XE-Feld einen Eintrag zu machen.
// Da wir uns auf Seite 2 mit "MySequence" bei 3 befinden, wird ", 3 on page 3" an denselben INDEX-Eintrag wie oben angehängt.
// Der Teil mit der Seitennummer dieses INDEX-Eintrags zeigt nun "MySequence at 1 on page 2, 3 on page 3" an.
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// Fügt ein XE-Feld mit einem neuen und eindeutigen Text-Eigenschaftswert ein.
// Dies fügt einen neuen Eintrag hinzu, mit MySequence bei 3 auf Seite 4.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### Siehe auch

* class [FieldIndex](../)
* namensraum [Aspose.Words.Fields](../../fieldindex/)
* Montage [Aspose.Words](../../../)


