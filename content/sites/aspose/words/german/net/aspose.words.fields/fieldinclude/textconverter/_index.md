---
title: FieldInclude.TextConverter
second_title: Aspose.Words für .NET-API-Referenz
description: FieldInclude eigendom. Liest oder setzt den Namen des Textkonverters für das Format der eingebundenen Datei.
type: docs
weight: 50
url: /de/net/aspose.words.fields/fieldinclude/textconverter/
---
## FieldInclude.TextConverter property

Liest oder setzt den Namen des Textkonverters für das Format der eingebundenen Datei.

```csharp
public string TextConverter { get; set; }
```

### Beispiele

Zeigt, wie ein INCLUDE-Feld erstellt und seine Eigenschaften festgelegt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wir können ein INCLUDE-Feld verwenden, um einen Teil eines anderen Dokuments in das lokale Dateisystem zu importieren.
// Das Lesezeichen aus dem anderen Dokument, auf das wir mit diesem Feld verweisen, enthält diesen importierten Teil.
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### Siehe auch

* class [FieldInclude](../)
* namensraum [Aspose.Words.Fields](../../fieldinclude/)
* Montage [Aspose.Words](../../../)


