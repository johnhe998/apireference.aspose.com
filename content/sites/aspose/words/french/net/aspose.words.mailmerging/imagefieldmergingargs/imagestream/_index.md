---
title: ImageFieldMergingArgs.ImageStream
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageFieldMergingArgs propriété. Spécifie le flux à partir duquel le moteur de publipostage lit une image.
type: docs
weight: 40
url: /fr/net/aspose.words.mailmerging/imagefieldmergingargs/imagestream/
---
## ImageFieldMergingArgs.ImageStream property

Spécifie le flux à partir duquel le moteur de publipostage lit une image.

```csharp
public Stream ImageStream { get; set; }
```

### Remarques

Aspose.Words ferme ce flux après avoir fusionné l'image dans le document.

### Exemples

Montre comment insérer des images stockées dans un champ BLOB de base de données dans un rapport.

```csharp
public void ImageFromBlob()
{
    Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

    doc.MailMerge.FieldMergingCallback = new HandleMergeImageFieldFromBlob();

    string connString = $"Provider=Microsoft.Jet.OLEDB.4.0;Data Source={DatabaseDir + "Northwind.mdb"};";
    string query = "SELECT FirstName, LastName, Title, Address, City, Region, Country, PhotoBLOB FROM Employees";

    using (OleDbConnection conn = new OleDbConnection(connString))
    {
        conn.Open();

        // Ouvre le lecteur de données, qui doit être dans un mode qui lit tous les enregistrements à la fois.
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // Ne fais rien.
    }

    /// <summary>
    /// Ceci est appelé lorsqu'un publipostage rencontre un MERGEFIELD dans le document avec une balise "Image :" dans son nom.
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

### Voir également

* class [ImageFieldMergingArgs](../)
* espace de noms [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* Assemblée [Aspose.Words](../../../)


