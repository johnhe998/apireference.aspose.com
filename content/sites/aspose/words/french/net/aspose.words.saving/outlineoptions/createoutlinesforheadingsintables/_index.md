---
title: OutlineOptions.CreateOutlinesForHeadingsInTables
second_title: Référence de l'API Aspose.Words pour .NET
description: OutlineOptions propriété. Spécifie sil faut ou non créer des contours pour les entêtes paragraphes formatés avec les styles dentête à lintérieur des tableaux.
type: docs
weight: 40
url: /fr/net/aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/
---
## OutlineOptions.CreateOutlinesForHeadingsInTables property

Spécifie s'il faut ou non créer des contours pour les en-têtes (paragraphes formatés avec les styles d'en-tête) à l'intérieur des tableaux.

```csharp
public bool CreateOutlinesForHeadingsInTables { get; set; }
```

### Remarques

La valeur par défaut est **faux**.

### Exemples

Montre comment créer des entrées de plan de document PDF pour les titres à l'intérieur des tableaux.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un tableau avec trois lignes. La première rangée,
// dont le texte sera formaté dans un style de type titre, servira d'en-tête de colonne.
builder.StartTable();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Customers");
builder.EndRow();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Normal;
builder.Write("John Doe");
builder.EndRow();
builder.InsertCell();
builder.Write("Jane Doe");
builder.EndTable();

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Le document PDF de sortie contiendra un plan, qui est une table des matières qui répertorie les en-têtes dans le corps du document.
// Cliquer sur une entrée dans ce plan nous amènera à l'emplacement de son en-tête respectif.
// Définissez la propriété "HeadingsOutlineLevels" à "1" pour obtenir le contour
// pour enregistrer uniquement les en-têtes avec des niveaux d'en-tête qui ne sont pas supérieurs à 1.
pdfSaveOptions.OutlineOptions.HeadingsOutlineLevels = 1;

// Définissez la propriété "CreateOutlinesForHeadingsInTables" sur "false" pour exclure tous les en-têtes des tableaux,
// tel que celui que nous avons créé ci-dessus à partir du contour.
// Définissez la propriété "CreateOutlinesForHeadingsInTables" sur "true" pour inclure tous les en-têtes dans les tableaux
// dans le plan, à condition qu'ils aient un niveau de titre qui ne soit pas supérieur à la valeur de la propriété "HeadingsOutlineLevels".
pdfSaveOptions.OutlineOptions.CreateOutlinesForHeadingsInTables = createOutlinesForHeadingsInTables;

doc.Save(ArtifactsDir + "PdfSaveOptions.TableHeadingOutlines.pdf", pdfSaveOptions);
```

### Voir également

* class [OutlineOptions](../)
* espace de noms [Aspose.Words.Saving](../../outlineoptions/)
* Assemblée [Aspose.Words](../../../)


