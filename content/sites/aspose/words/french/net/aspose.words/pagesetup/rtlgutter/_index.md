---
title: PageSetup.RtlGutter
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Obtient ou définit si Microsoft Word utilise des gouttières pour la section basée sur une langue de droite à gauche ou une langue de gauche à droite.
type: docs
weight: 370
url: /fr/net/aspose.words/pagesetup/rtlgutter/
---
## PageSetup.RtlGutter property

Obtient ou définit si Microsoft Word utilise des gouttières pour la section basée sur une langue de droite à gauche ou une langue de gauche à droite.

```csharp
public bool RtlGutter { get; set; }
```

### Exemples

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

* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


