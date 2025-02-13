---
title: PageSetup.MultiplePages
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Pour les documents de plusieurs pages obtient ou définit la manière dont un document est imprimé ou rendu afin quil puisse être relié sous forme de livret.
type: docs
weight: 260
url: /fr/net/aspose.words/pagesetup/multiplepages/
---
## PageSetup.MultiplePages property

Pour les documents de plusieurs pages, obtient ou définit la manière dont un document est imprimé ou rendu afin qu'il puisse être relié sous forme de livret.

```csharp
public MultiplePagesType MultiplePages { get; set; }
```

### Exemples

Montre comment configurer un document pouvant être imprimé sous forme de pli de livre.

```csharp
Document doc = new Document();

// Insère un texte qui s'étend sur 16 pages.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("My Booklet:");

for (int i = 0; i < 15; i++)
{
    builder.InsertBreak(BreakType.PageBreak);
    builder.Write($"Booklet face #{i}");
}

// Configurez la propriété "PageSetup" de la première section pour imprimer le document sous la forme d'un pli de livre.
// Quand on imprime ce document recto verso, on peut prendre les pages pour les empiler
// et pliez-les tous au milieu à la fois. Le contenu du document s'alignera dans un pli de livre.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;

// Nous ne pouvons spécifier le nombre de feuilles qu'en multiples de 4.
pageSetup.SheetsPerBooklet = 4;

doc.Save(ArtifactsDir + "PageSetup.Booklet.docx");
```

Montre comment définir les marges de gouttière.

```csharp
Document doc = new Document();

// Insère du texte qui s'étend sur plusieurs pages.
DocumentBuilder builder = new DocumentBuilder(doc);
for (int i = 0; i < 6; i++)
{
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                  "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
    builder.InsertBreak(BreakType.PageBreak);
}

// Une gouttière ajoute des espaces blancs à la marge gauche ou droite de la page,
// qui compense le pliage central des pages d'un livre qui empiète sur la mise en page de la page.
PageSetup pageSetup = doc.Sections[0].PageSetup;

 // Déterminez l'espace de nos pages pour le texte dans les marges, puis ajoutez un montant pour remplir une marge.
Assert.AreEqual(470.30d, pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin, 0.01d);

pageSetup.Gutter = 100.0d;

// Définissez la propriété "RtlGutter" sur "true" pour placer la gouttière dans une position plus appropriée pour le texte de droite à gauche.
pageSetup.RtlGutter = true;

// Définissez la propriété "MultiplePages" sur "MultiplePagesType.MirrorMargins" pour alterner
// la position gauche/droite des marges sur chaque page.
pageSetup.MultiplePages = MultiplePagesType.MirrorMargins;

doc.Save(ArtifactsDir + "PageSetup.Gutter.docx");
```

### Voir également

* enum [MultiplePagesType](../../../aspose.words.settings/multiplepagestype/)
* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


