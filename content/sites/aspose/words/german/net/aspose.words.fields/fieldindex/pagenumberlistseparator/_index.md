---
title: FieldIndex.PageNumberListSeparator
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIndex eigendom. Ruft die Zeichenfolge ab oder legt sie fest die verwendet wird um zwei Seitenzahlen in einer Seitenzahlenliste zu trennen.
type: docs
weight: 110
url: /de/net/aspose.words.fields/fieldindex/pagenumberlistseparator/
---
## FieldIndex.PageNumberListSeparator property

Ruft die Zeichenfolge ab oder legt sie fest, die verwendet wird, um zwei Seitenzahlen in einer Seitenzahlenliste zu trennen.

```csharp
public string PageNumberListSeparator { get; set; }
```

### Beispiele

Zeigt, wie das Seitenzahlentrennzeichen in einem INDEX-Feld bearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an,
// und die Nummer der Seite, die rechts das XE-Feld enthält.
// Der INDEX-Eintrag gruppiert XE-Felder mit übereinstimmenden Werten in der Eigenschaft "Text".
// in einen Eintrag anstatt für jedes XE-Feld einen Eintrag zu machen.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Wenn unser INDEX-Feld einen Eintrag für eine Gruppe von XE-Feldern hat,
// Dieser Eintrag zeigt die Nummer jeder Seite an, die ein XE-Feld enthält, das zu dieser Gruppe gehört.
// Wir können benutzerdefinierte Trennzeichen festlegen, um das Erscheinungsbild dieser Seitenzahlen anzupassen.
index.PageNumberSeparator = ", on page(s) ";
index.PageNumberListSeparator = " & ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\l \" & \"", index.GetFieldCode());
Assert.True(index.HasPageNumberSeparator);

// Nachdem wir diese XE-Felder eingefügt haben, zeigt das INDEX-Feld "Erster Eintrag, auf Seite(n) 2 & 3 & 4" an.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

Assert.AreEqual(" XE  \"First entry\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageNumberList.docx");
```

### Siehe auch

* class [FieldIndex](../)
* namensraum [Aspose.Words.Fields](../../fieldindex/)
* Montage [Aspose.Words](../../../)


