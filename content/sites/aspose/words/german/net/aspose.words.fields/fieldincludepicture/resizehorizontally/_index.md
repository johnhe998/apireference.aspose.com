---
title: FieldIncludePicture.ResizeHorizontally
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIncludePicture eigendom. Ruft ab oder legt fest ob die Größe des Bilds horizontal von der Quelle geändert werden soll.
type: docs
weight: 40
url: /de/net/aspose.words.fields/fieldincludepicture/resizehorizontally/
---
## FieldIncludePicture.ResizeHorizontally property

Ruft ab oder legt fest, ob die Größe des Bilds horizontal von der Quelle geändert werden soll.

```csharp
public bool ResizeHorizontally { get; set; }
```

### Beispiele

Zeigt, wie Bilder mit den Feldern IMPORT und INCLUDEPICTURE eingefügt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Unten sind zwei ähnliche Feldtypen, die wir verwenden können, um Bilder anzuzeigen, die vom lokalen Dateisystem verlinkt sind.
// 1 - Das INCLUDEPICTURE-Feld:
FieldIncludePicture fieldIncludePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
fieldIncludePicture.SourceFullName = ImageDir + "Transparent background logo.png";

Assert.True(Regex.Match(fieldIncludePicture.GetFieldCode(), " INCLUDEPICTURE  .*").Success);

// Den PNG32.FLT-Filter anwenden.
fieldIncludePicture.GraphicFilter = "PNG32";
fieldIncludePicture.IsLinked = true;
fieldIncludePicture.ResizeHorizontally = true;
fieldIncludePicture.ResizeVertically = true;

// 2 - Das IMPORT-Feld:
FieldImport fieldImport = (FieldImport)builder.InsertField(FieldType.FieldImport, true);
fieldImport.SourceFullName = ImageDir + "Transparent background logo.png";
fieldImport.GraphicFilter = "PNG32";
fieldImport.IsLinked = true;

Assert.True(Regex.Match(fieldImport.GetFieldCode(), " IMPORT  .* \\\\c PNG32 \\\\d").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IMPORT.INCLUDEPICTURE.docx");
```

### Siehe auch

* class [FieldIncludePicture](../)
* namensraum [Aspose.Words.Fields](../../fieldincludepicture/)
* Montage [Aspose.Words](../../../)


