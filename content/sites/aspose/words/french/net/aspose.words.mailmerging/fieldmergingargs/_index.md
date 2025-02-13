---
title: Class FieldMergingArgs
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.MailMerging.FieldMergingArgs classe. Fournit des données pour le Champ de fusion événement.
type: docs
weight: 3550
url: /fr/net/aspose.words.mailmerging/fieldmergingargs/
---
## FieldMergingArgs class

Fournit des données pour le **Champ de fusion** événement.

```csharp
public class FieldMergingArgs : FieldMergingArgsBase
```

## Propriétés

| Nom | La description |
| --- | --- |
| [Document](../../aspose.words.mailmerging/fieldmergingargsbase/document/) { get; } | Renvoie le[`Document`](../fieldmergingargsbase/document/) objet pour lequel le publipostage est effectué. |
| [DocumentFieldName](../../aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/) { get; } | Obtient le nom du champ de fusion tel que spécifié dans le document. |
| [Field](../../aspose.words.mailmerging/fieldmergingargsbase/field/) { get; } | Obtient l'objet qui représente le champ de fusion actuel. |
| [FieldName](../../aspose.words.mailmerging/fieldmergingargsbase/fieldname/) { get; } | Obtient le nom du champ de fusion dans la source de données. |
| [FieldValue](../../aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/) { get; set; } | Obtient ou définit la valeur du champ à partir de la source de données. |
| [RecordIndex](../../aspose.words.mailmerging/fieldmergingargsbase/recordindex/) { get; } | Obtient l'index de base zéro de l'enregistrement en cours de fusion. |
| [TableName](../../aspose.words.mailmerging/fieldmergingargsbase/tablename/) { get; } | Obtient le nom de la table de données pour l'opération de fusion en cours ou une chaîne vide si le nom n'est pas disponible. |
| [Text](../../aspose.words.mailmerging/fieldmergingargs/text/) { get; set; } | Obtient ou définit le texte qui sera inséré dans le document pour le champ de fusion actuel. |

### Remarques

La **Champ de fusion** se produit pendant le publipostage lorsqu'un simple champ publipostage est rencontré dans le document. Vous pouvez répondre à cet événement en retournant texte pour que le moteur de publipostage l'insère dans le document.

### Exemples

Montre comment exécuter un publipostage avec un rappel personnalisé qui gère les données de fusion sous la forme de documents HTML.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(@"MERGEFIELD  html_Title  \b Content");
    builder.InsertField(@"MERGEFIELD  html_Body  \b Content");

    object[] mergeData =
    {
        "<html>" +
            "<h1>" +
                "<span style=\"color: #0000ff; font-family: Arial;\">Hello World!</span>" +
            "</h1>" +
        "</html>", 

        "<html>" +
            "<blockquote>" +
                "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>" +
            "</blockquote>" +
        "</html>"
    };

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertHtml();
    doc.MailMerge.Execute(new[] { "html_Title", "html_Body" }, mergeData);

    doc.Save(ArtifactsDir + "MailMergeEvent.MergeHtml.docx");
}

/// <summary>
/// Si le publipostage rencontre un MERGEFIELD dont le nom commence par le préfixe "html_",
/// ce rappel analyse ses données de fusion en tant que contenu HTML et ajoute le résultat à l'emplacement du document du MERGEFIELD.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// Appelé lorsqu'un publipostage fusionne des données dans un MERGEFIELD.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // Ajoute des données HTML analysées au corps du document.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // Puisque nous avons déjà inséré manuellement le contenu fusionné,
             // nous n'aurons pas besoin de répondre à cet événement en renvoyant du contenu via la propriété "Texte".
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Ne fais rien.
    }
}
```

### Voir également

* class [FieldMergingArgsBase](../fieldmergingargsbase/)
* espace de noms [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* Assemblée [Aspose.Words](../../)


