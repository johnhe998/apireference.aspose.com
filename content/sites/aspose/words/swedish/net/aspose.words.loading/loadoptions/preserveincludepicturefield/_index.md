---
title: LoadOptions.PreserveIncludePictureField
second_title: Aspose.Words för .NET API Referens
description: LoadOptions fast egendom. Hämtar eller ställer in om fältet INCLUDEPICTURE ska bevaras vid läsning av Microsoft Wordformat. Standardvärdet är false.
type: docs
weight: 120
url: /sv/net/aspose.words.loading/loadoptions/preserveincludepicturefield/
---
## LoadOptions.PreserveIncludePictureField property

Hämtar eller ställer in om fältet INCLUDEPICTURE ska bevaras vid läsning av Microsoft Word-format. Standardvärdet är false.

```csharp
public bool PreserveIncludePictureField { get; set; }
```

### Anmärkningar

Som standard konverteras fältet INCLUDEPICTURE till ett formobjekt. Du kan åsidosätta det om du behöver att fältet ska bevaras, till exempel om du vill uppdatera det programmatiskt. Observera dock att detta tillvägagångssätt inte är vanligt för Aspose.Words. Använd den på egen risk.

Ett av de möjliga användningsfallen kan vara att använda ett MERGEFIELD som ett underordnat fält för att dynamiskt ändra bildens källsökväg . I det här fallet behöver du INKLUDERA BILDEN bevaras i modellen.

### Exempel

Visar hur man bevarar eller kasserar INCLUDEPICTURE-fält när ett dokument laddas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldIncludePicture includePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
includePicture.SourceFullName = ImageDir + "Transparent background logo.png";
includePicture.Update(true);

using (MemoryStream docStream = new MemoryStream())
{
    doc.Save(docStream, new OoxmlSaveOptions(SaveFormat.Docx));

    // Vi kan sätta en flagga i ett LoadOptions-objekt för att bestämma om alla INCLUDEPICTURE-fält ska konverteras
    // till bildformer när du laddar ett dokument som innehåller dem.
    LoadOptions loadOptions = new LoadOptions
    {
        PreserveIncludePictureField = preserveIncludePictureField
    };

    doc = new Document(docStream, loadOptions);

    if (preserveIncludePictureField)
    {
        Assert.True(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));

        doc.UpdateFields();
        doc.Save(ArtifactsDir + "Field.PreserveIncludePicture.docx");
    }
    else
    {
        Assert.False(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));
    }
}
```

### Se även

* class [LoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../loadoptions/)
* hopsättning [Aspose.Words](../../../)


