---
title: ImageFieldMergingArgs.Image
second_title: Aspose.Words för .NET API Referens
description: ImageFieldMergingArgs fast egendom. Anger bilden som kopplingsmotorn måste infoga i dokumentet.
type: docs
weight: 10
url: /sv/net/aspose.words.mailmerging/imagefieldmergingargs/image/
---
## ImageFieldMergingArgs.Image property

Anger bilden som kopplingsmotorn måste infoga i dokumentet.

```csharp
public Image Image { get; set; }
```

### Exempel

Visar hur man använder en återuppringning för att anpassa bildsammanslagningslogik.

```csharp
{
    Document doc = new Document();

    // Infoga ett MERGEFIELD som kommer att acceptera bilder från en källa under en e-postkoppling. Använd fältkoden för att referera
    // en kolumn i datakällan som innehåller lokala systemfilnamn på bilder som vi vill använda i kopplingen.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // I det här fallet förväntar fältet att datakällan har en sådan kolumn med namnet "ImageColumn".
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // Filnamn kan vara långa, och om vi kan hitta ett sätt att undvika att lagra dem i datakällan,
    // vi kan minska dess storlek avsevärt.
    // Skapa en datakälla som refererar till bilder med korta namn.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add("Dark logo");
    dataTable.Rows.Add("Transparent logo");

    // Tilldela en sammanslagningsåteruppringning som innehåller all logik som behandlar dessa namn,
      // och kör sedan sammanslagningen.
    doc.MailMerge.FieldMergingCallback = new ImageFilenameCallback();
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "Field.MERGEFIELD.Images.docx");

/// <summary>
/// Innehåller en ordbok som mappar namn på bilder till lokala systemfilnamn som innehåller dessa bilder.
/// Om en kopplingsdatakälla använder ett av ordbokens namn för att referera till en bild,
/// denna återuppringning kommer att skicka respektive filnamn till sammanslagningsdestinationen.
/// </summary>
private class ImageFilenameCallback : IFieldMergingCallback
{
    public ImageFilenameCallback()
    {
        mImageFilenames = new Dictionary<string, string>();
        mImageFilenames.Add("Dark logo", ImageDir + "Logo.jpg");
        mImageFilenames.Add("Transparent logo", ImageDir + "Transparent background logo.png");
    }

    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        throw new NotImplementedException();
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        if (mImageFilenames.ContainsKey(args.FieldValue.ToString()))
        {
            #if NET48 || JAVA
            args.Image = Image.FromFile(mImageFilenames[args.FieldValue.ToString()]);
            #elif NET5_0_OR_GREATER
            args.Image = SKBitmap.Decode(mImageFilenames[args.FieldValue.ToString()]);
            args.ImageFileName = mImageFilenames[args.FieldValue.ToString()];
            #endif
        }

        Assert.NotNull(args.Image);
    }

    private readonly Dictionary<string, string> mImageFilenames;
}
```

### Se även

* class [ImageFieldMergingArgs](../)
* namnutrymme [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* hopsättning [Aspose.Words](../../../)


