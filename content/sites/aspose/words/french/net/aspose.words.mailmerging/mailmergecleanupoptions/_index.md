---
title: Enum MailMergeCleanupOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.MailMerging.MailMergeCleanupOptions énumération. Spécifie les options qui déterminent quels éléments sont supprimés lors du publipostage.
type: docs
weight: 3630
url: /fr/net/aspose.words.mailmerging/mailmergecleanupoptions/
---
## MailMergeCleanupOptions enumeration

Spécifie les options qui déterminent quels éléments sont supprimés lors du publipostage.

```csharp
[Flags]
public enum MailMergeCleanupOptions
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| None | `0` | Spécifie une valeur par défaut. |
| RemoveEmptyParagraphs | `1` | Spécifie si les paragraphes contenant des champs de fusion et publipostage sans données doivent être supprimés du document. Lorsque cette option est définie, les paragraphes contenant des champs de fusion de début et de fin de région qui sont autrement vides sont également supprimés. |
| RemoveUnusedRegions | `2` | Spécifie si les régions de fusion et publipostage inutilisées doivent être supprimées du document. |
| RemoveUnusedFields | `4` | Spécifie si les champs de fusion inutilisés doivent être supprimés du document. |
| RemoveContainingFields | `8` | Spécifie si les champs qui contiennent des champs de fusion (par exemple, les IF) doivent être supprimés du document si les champs de fusion imbriqués sont supprimés. |
| RemoveStaticFields | `10` | Spécifie si les champs statiques doivent être supprimés du document. Les champs statiques sont des champs dont les résultats restent les mêmes lors de toute modification de document. Les champs, qui ne stockent pas leurs résultats dans un document et sont calculés à la volée (commeFieldListNum , FieldSymbol , etc.) ne sont pas considérés comme statiques. |
| RemoveEmptyTableRows | `20` | Spécifie si les lignes vides contenant des régions de fusion et publipostage doivent être supprimées du document. |

### Exemples

Montre comment supprimer les paragraphes vides qu'un publipostage peut créer à partir du document de sortie de la fusion.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD TableStart:MyTable");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertField(" MERGEFIELD TableEnd:MyTable");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "", "" });
dataTable.Rows.Add(new object[] { "Jane", "Doe" });

doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.ExecuteWithRegions(dataTable);

if (doc.MailMerge.CleanupOptions == MailMergeCleanupOptions.RemoveEmptyParagraphs) 
    Assert.AreEqual(
        "John Doe\r" +
        "Jane Doe", doc.GetText().Trim());
else
    Assert.AreEqual(
        "John Doe\r" +
        " \r" +
        "Jane Doe", doc.GetText().Trim());
```

Montre comment supprimer automatiquement les MERGEFIELD inutilisés lors du publipostage.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un document avec MERGEFIELDs pour trois colonnes d'une table de source de données de publipostage,
// puis créez une table avec seulement deux colonnes dont les noms correspondent à nos MERGEFIELDs.
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "Joe", "Bloggs" });

// Notre troisième MERGEFIELD fait référence à une colonne "Ville", qui n'existe pas dans notre source de données.
// Le publipostage laissera des champs tels que celui-ci intacts dans leur état de pré-fusion.
// Définir la propriété "CleanupOptions" sur "RemoveUnusedFields" supprimera tous les MERGEFIELD
// qui ne sont pas utilisés lors d'un publipostage pour nettoyer les documents de fusion.
doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.Execute(dataTable);

if (mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveUnusedFields || 
    mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveStaticFields)
    Assert.AreEqual(0, doc.Range.Fields.Count);
else
    Assert.AreEqual(2, doc.Range.Fields.Count);
```

### Voir également

* espace de noms [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* Assemblée [Aspose.Words](../../)


