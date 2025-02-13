---
title: FieldIndex.PageRangeSeparator
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIndex eigendom. Ruft die Zeichenfolge ab oder legt sie fest die verwendet wird um den Anfang und das Ende eines Seitenbereichs zu trennen.
type: docs
weight: 130
url: /de/net/aspose.words.fields/fieldindex/pagerangeseparator/
---
## FieldIndex.PageRangeSeparator property

Ruft die Zeichenfolge ab oder legt sie fest, die verwendet wird, um den Anfang und das Ende eines Seitenbereichs zu trennen.

```csharp
public string PageRangeSeparator { get; set; }
```

### Beispiele

Zeigt, wie die überspannten Seiten eines Lesezeichens als Seitenbereich für einen INDEX-Feldeintrag angegeben werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie ein INDEX-Feld, das einen Eintrag für jedes im Dokument gefundene XE-Feld anzeigt.
// Jeder Eintrag zeigt den Text-Eigenschaftswert des XE-Felds auf der linken Seite an,
// und die Nummer der Seite, die rechts das XE-Feld enthält.
// Der INDEX-Eintrag sammelt alle XE-Felder mit übereinstimmenden Werten in der Eigenschaft "Text".
// in einen Eintrag anstatt für jedes XE-Feld einen Eintrag zu machen.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Für INDEX-Einträge, die Seitenbereiche anzeigen, können wir eine Trennzeichenfolge angeben
// die zwischen der Nummer der ersten Seite und der Nummer der letzten erscheint.
index.PageNumberSeparator = ", on page(s) ";
index.PageRangeSeparator = " to ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\g \" to \"", index.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "My entry";

// Wenn ein XE-Feld ein Lesezeichen mit der Eigenschaft PageRangeBookmarkName benennt,
// sein INDEX-Eintrag zeigt den Seitenbereich an, den das Lesezeichen umfasst
// anstelle der Nummer der Seite, die das XE-Feld enthält.
indexEntry.PageRangeBookmarkName = "MyBookmark";

Assert.AreEqual(" XE  \"My entry\" \\r MyBookmark", indexEntry.GetFieldCode());
Assert.AreEqual("MyBookmark", indexEntry.PageRangeBookmarkName);

// Lesezeichen einfügen, das auf Seite 3 beginnt und auf Seite 5 endet.
// Der INDEX-Eintrag für das XE-Feld, das auf dieses Lesezeichen verweist, zeigt diesen Seitenbereich an.
// In unserer Tabelle zeigt der INDEX-Eintrag "Mein Eintrag, auf Seite(n) 3 bis 5" an.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MyBookmark");
builder.Write("Start of MyBookmark");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.Write("End of MyBookmark");
builder.EndBookmark("MyBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageRangeBookmark.docx");
```

### Siehe auch

* class [FieldIndex](../)
* namensraum [Aspose.Words.Fields](../../fieldindex/)
* Montage [Aspose.Words](../../../)


