---
title: Document.MailMerge
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Renvoie un Publipostage objet qui représente la fonctionnalité de fusion et publipostage pour le document.
type: docs
weight: 240
url: /fr/net/aspose.words/document/mailmerge/
---
## Document.MailMerge property

Renvoie un **Publipostage** objet qui représente la fonctionnalité de fusion et publipostage pour le document.

```csharp
public MailMerge MailMerge { get; }
```

### Exemples

Montre comment exécuter un publipostage avec les données d'un DataTable.

```csharp
public void ExecuteDataTable()
{
    DataTable table = new DataTable("Test");
    table.Columns.Add("CustomerName");
    table.Columns.Add("Address");
    table.Rows.Add(new object[] { "Thomas Hardy", "120 Hanover Sq., London" });
    table.Rows.Add(new object[] { "Paolo Accorti", "Via Monte Bianco 34, Torino" });

    // Vous trouverez ci-dessous deux manières d'utiliser un DataTable comme source de données pour un publipostage.
    // 1 - Utiliser le tableau entier pour le publipostage afin de créer un document de publipostage de sortie pour chaque ligne du tableau :
    Document doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.WholeTable.docx");

    // 2 - Utilisez une ligne du tableau pour créer un document de publipostage de sortie :
    doc = CreateSourceDocExecuteDataTable();

    doc.MailMerge.Execute(table.Rows[1]);

    doc.Save(ArtifactsDir + "MailMerge.ExecuteDataTable.OneRow.docx");
}

/// <summary>
/// Crée un document source de fusion et publipostage.
/// </summary>
private static Document CreateSourceDocExecuteDataTable()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD CustomerName ");
    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD Address ");

    return doc;
}
```

### Voir également

* class [MailMerge](../../../aspose.words.mailmerging/mailmerge/)
* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


