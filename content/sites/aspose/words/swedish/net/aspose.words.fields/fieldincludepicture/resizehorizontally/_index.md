---
title: FieldIncludePicture.ResizeHorizontally
second_title: Aspose.Words för .NET API Referens
description: FieldIncludePicture fast egendom. Hämtar eller ställer in om storleken på bilden ska ändras horisontellt från källan.
type: docs
weight: 40
url: /sv/net/aspose.words.fields/fieldincludepicture/resizehorizontally/
---
## FieldIncludePicture.ResizeHorizontally property

Hämtar eller ställer in om storleken på bilden ska ändras horisontellt från källan.

```csharp
public bool ResizeHorizontally { get; set; }
```

### Exempel

Visar hur man infogar bilder med hjälp av IMPORT- och INCLUDEPICTURE-fälten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nedan finns två liknande fälttyper som vi kan använda för att visa bilder länkade från det lokala filsystemet.
// 1 - Fältet INKLUDERA BILD:
FieldIncludePicture fieldIncludePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
fieldIncludePicture.SourceFullName = ImageDir + "Transparent background logo.png";

Assert.True(Regex.Match(fieldIncludePicture.GetFieldCode(), " INCLUDEPICTURE  .*").Success);

// Använd PNG32.FLT-filtret.
fieldIncludePicture.GraphicFilter = "PNG32";
fieldIncludePicture.IsLinked = true;
fieldIncludePicture.ResizeHorizontally = true;
fieldIncludePicture.ResizeVertically = true;

// 2 - IMPORT-fältet:
FieldImport fieldImport = (FieldImport)builder.InsertField(FieldType.FieldImport, true);
fieldImport.SourceFullName = ImageDir + "Transparent background logo.png";
fieldImport.GraphicFilter = "PNG32";
fieldImport.IsLinked = true;

Assert.True(Regex.Match(fieldImport.GetFieldCode(), " IMPORT  .* \\\\c PNG32 \\\\d").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IMPORT.INCLUDEPICTURE.docx");
```

### Se även

* class [FieldIncludePicture](../)
* namnutrymme [Aspose.Words.Fields](../../fieldincludepicture/)
* hopsättning [Aspose.Words](../../../)


