---
title: FieldOptions.FileName
second_title: Aspose.Words för .NET API Referens
description: FieldOptions fast egendom. Hämtar eller ställer in filnamnet på dokumentet.
type: docs
weight: 120
url: /sv/net/aspose.words.fields/fieldoptions/filename/
---
## FieldOptions.FileName property

Hämtar eller ställer in filnamnet på dokumentet.

```csharp
public string FileName { get; set; }
```

### Anmärkningar

Den här egenskapen används av[`FieldFileName`](../../fieldfilename/) fält med högre prioritet än[`OriginalFileName`](../../../aspose.words/document/originalfilename/) fast egendom.

### Exempel

Visar hur man använder FieldOptions för att åsidosätta standardvärdet för fältet FILNAMN.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// Detta FILNAMN-fält kommer att visa det lokala systemfilnamnet för dokumentet vi laddade.
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// Som standard visar fältet FILNAMN filens namn, men inte dess fullständiga sökväg till det lokala filsystemet.
// Vi kan ställa in en flagga för att få den att visa hela filsökvägen.
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// Vi kan också ställa in ett värde för denna egenskap till
// åsidosätt värdet som fältet FILNAMN visar.
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### Se även

* class [FieldOptions](../)
* namnutrymme [Aspose.Words.Fields](../../fieldoptions/)
* hopsättning [Aspose.Words](../../../)


