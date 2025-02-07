---
title: FieldXE.Text
second_title: Aspose.Words für .NET-API-Referenz
description: FieldXE eigendom. Liest oder setzt den Text des Eintrags.
type: docs
weight: 70
url: /de/net/aspose.words.fields/fieldxe/text/
---
## FieldXE.Text property

Liest oder setzt den Text des Eintrags.

```csharp
public string Text { get; set; }
```

### Beispiele

Zeigt, wie Sie ein INDEX-Feld erstellen und es dann mithilfe von XE-Feldern mit Einträgen füllen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an
// und rechts die Seite mit dem XE-Feld.
// Wenn die XE-Felder den gleichen Wert in ihrer "Text"-Eigenschaft haben,
// das Feld INDEX gruppiert sie zu einem Eintrag.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Konfigurieren Sie das INDEX-Feld nur so, dass XE-Felder angezeigt werden, die innerhalb der Grenzen liegen
// eines Lesezeichens mit dem Namen "MainBookmark" und dessen "EntryType"-Eigenschaften den Wert "A" haben.
// Sowohl für INDEX- als auch für XE-Felder verwendet die Eigenschaft "EntryType" nur das erste Zeichen ihres Zeichenfolgenwerts.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// Beginnen Sie auf einer neuen Seite das Lesezeichen mit einem Namen, der dem Wert entspricht
// der Eigenschaft "BookmarkName" des INDEX-Felds.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// Das INDEX-Feld nimmt diesen Eintrag auf, da er sich innerhalb des Lesezeichens befindet,
// und sein Eintragstyp stimmt auch mit dem Eintragstyp des INDEX-Felds überein.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// Fügen Sie ein XE-Feld ein, das nicht im INDEX erscheint, da die Eintragstypen nicht übereinstimmen.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// Lesezeichen beenden und danach ein XE-Feld einfügen.
// Es ist vom gleichen Typ wie das INDEX-Feld, wird aber nicht angezeigt
// da es außerhalb der Grenzen des Lesezeichens liegt.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

Zeigt, wie ein INDEX-Feld mithilfe von XE-Feldern mit Einträgen gefüllt und sein Erscheinungsbild geändert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an,
// und die Nummer der Seite, die rechts das XE-Feld enthält.
// Wenn die XE-Felder den gleichen Wert in ihrer "Text"-Eigenschaft haben,
// das Feld INDEX gruppiert sie zu einem Eintrag.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.LanguageId = "1033";

// Wenn Sie den Wert dieser Eigenschaft auf "A" setzen, werden alle Einträge nach ihrem Anfangsbuchstaben gruppiert,
// und platzieren Sie diesen Buchstaben in Großbuchstaben über jeder Gruppe.
index.Heading = "A";

// Stellen Sie die vom INDEX-Feld erstellte Tabelle so ein, dass sie sich über 2 Spalten erstreckt.
index.NumberOfColumns = "2";

// Alle Einträge mit Anfangsbuchstaben außerhalb des "ac"-Zeichenbereichs so einstellen, dass sie weggelassen werden.
index.LetterRange = "a-c";

Assert.AreEqual(" INDEX  \\z 1033 \\h A \\c 2 \\p a-c", index.GetFieldCode());

// Diese nächsten beiden XE-Felder werden unter der Überschrift "A" angezeigt,
// mit ihren jeweiligen Textstilen, die auch auf ihre Seitenzahlen angewendet werden.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";
indexEntry.IsItalic = true;

Assert.AreEqual(" XE  Apple \\i", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apricot";
indexEntry.IsBold = true;

Assert.AreEqual(" XE  Apricot \\b", indexEntry.GetFieldCode());

// Die beiden nächsten beiden XE-Felder werden im Inhaltsverzeichnis der INDEX-Felder unter einer "B"- und einer "C"-Überschrift stehen.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cherry";

// INDEX-Felder sortieren alle Einträge alphabetisch, sodass dieser Eintrag unter "A" mit den anderen beiden angezeigt wird.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Avocado";

// Dieser Eintrag erscheint nicht, da er mit dem Buchstaben "D" beginnt,
// die außerhalb des "ac"-Zeichenbereichs liegt, den die LetterRange-Eigenschaft des INDEX-Felds definiert.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Durian";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Formatting.docx");
```

### Siehe auch

* class [FieldXE](../)
* namensraum [Aspose.Words.Fields](../../fieldxe/)
* Montage [Aspose.Words](../../../)


