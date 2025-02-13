---
title: ImageFieldMergingArgs.Image
second_title: Aspose.Words für .NET-API-Referenz
description: ImageFieldMergingArgs eigendom. Gibt das Bild an das das Serienbriefmodul in das Dokument einfügen muss.
type: docs
weight: 10
url: /de/net/aspose.words.mailmerging/imagefieldmergingargs/image/
---
## ImageFieldMergingArgs.Image property

Gibt das Bild an, das das Serienbriefmodul in das Dokument einfügen muss.

```csharp
public Image Image { get; set; }
```

### Beispiele

Zeigt, wie ein Rückruf verwendet wird, um die Bildzusammenführungslogik anzupassen.

```csharp
{
    Document doc = new Document();

    // Fügen Sie ein MERGEFIELD ein, das Bilder von einer Quelle während eines Seriendrucks akzeptiert. Verwenden Sie den Feldcode zum Verweisen
    // eine Spalte in der Datenquelle, die lokale Systemdateinamen von Bildern enthält, die wir beim Seriendruck verwenden möchten.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // In diesem Fall erwartet das Feld, dass die Datenquelle eine solche Spalte mit dem Namen "ImageColumn" hat.
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // Dateinamen können lang sein, und wenn wir einen Weg finden können, sie nicht in der Datenquelle zu speichern,
    // Wir können seine Größe erheblich reduzieren.
    // Erstellen Sie eine Datenquelle, die mit Kurznamen auf Bilder verweist.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add("Dark logo");
    dataTable.Rows.Add("Transparent logo");

    // Weisen Sie einen Zusammenführungs-Callback zu, der die gesamte Logik enthält, die diese Namen verarbeitet,
     // und dann den Seriendruck ausführen.
    doc.MailMerge.FieldMergingCallback = new ImageFilenameCallback();
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "Field.MERGEFIELD.Images.docx");

/// <summary>
/// Enthält ein Wörterbuch, das Namen von Bildern lokalen Systemdateinamen zuordnet, die diese Bilder enthalten.
/// Wenn eine Seriendruck-Datenquelle einen der Namen des Wörterbuchs verwendet, um auf ein Bild zu verweisen,
/// Dieser Callback übergibt den jeweiligen Dateinamen an das Zusammenführungsziel.
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

### Siehe auch

* class [ImageFieldMergingArgs](../)
* namensraum [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* Montage [Aspose.Words](../../../)


