---
title: Class LayoutOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Layout.LayoutOptions classe. Contient les options qui permettent de contrôler le processus de mise en page du document.
type: docs
weight: 3150
url: /fr/net/aspose.words.layout/layoutoptions/
---
## LayoutOptions class

Contient les options qui permettent de contrôler le processus de mise en page du document.

```csharp
public class LayoutOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [LayoutOptions](layoutoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Callback](../../aspose.words.layout/layoutoptions/callback/) { get; set; } | Obtient ou définit[`IPageLayoutCallback`](../ipagelayoutcallback/)implémentation utilisée par le modèle de mise en page. |
| [CommentDisplayMode](../../aspose.words.layout/layoutoptions/commentdisplaymode/) { get; set; } | Obtient ou définit la façon dont les commentaires sont rendus. La valeur par défaut estShowInBalloons . |
| [ContinuousSectionPageNumberingRestart](../../aspose.words.layout/layoutoptions/continuoussectionpagenumberingrestart/) { get; set; } | Obtient ou définit le mode de comportement pour le calcul des numéros de page lorsqu'une section continue redémarre la numérotation des pages. |
| [IgnorePrinterMetrics](../../aspose.words.layout/layoutoptions/ignoreprintermetrics/) { get; set; } | Obtient ou définit une indication indiquant si l'option de compatibilité "Utiliser les mesures de l'imprimante pour mettre en page le document" est ignorée. La valeur par défaut est True. |
| [RevisionOptions](../../aspose.words.layout/layoutoptions/revisionoptions/) { get; } | Obtient les options de révision. |
| [ShowHiddenText](../../aspose.words.layout/layoutoptions/showhiddentext/) { get; set; } | Obtient ou définit une indication indiquant si le texte masqué dans le document est rendu. La valeur par défaut est False. |
| [ShowParagraphMarks](../../aspose.words.layout/layoutoptions/showparagraphmarks/) { get; set; } | Obtient ou définit l'indication du rendu des marques de paragraphe. La valeur par défaut est False. |
| [TextShaperFactory](../../aspose.words.layout/layoutoptions/textshaperfactory/) { get; set; } | Obtient ou définit[`ITextShaperFactory`](../../aspose.words.shaping/itextshaperfactory/) implémentation utilisée pour les fonctionnalités de rendu de typographie avancée. |

### Remarques

Vous ne créez pas directement des instances de cette classe. Utilisez le[`LayoutOptions`](../../aspose.words/document/layoutoptions/)propriété pour accéder aux options de mise en page de ce document.

Notez qu'après avoir modifié l'une des options présentes dans cette classe,[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) method doit être appelée pour que les options modifiées soient appliquées à la mise en page.

### Exemples

Montre comment masquer du texte dans un document de sortie rendu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Insérer du texte masqué, puis spécifier si nous souhaitons l'omettre d'un document rendu.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

Montre comment afficher les marques de paragraphe dans un document de sortie rendu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Ajoutez des paragraphes, puis activez les marques de paragraphe pour afficher la fin des paragraphes
// avec un symbole pilcrow (¶) lors du rendu du document.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

Montre comment modifier l'apparence des révisions dans un document de sortie rendu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une révision, puis change la couleur de toutes les révisions en vert.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Supprime la barre qui apparaît à gauche de chaque ligne révisée.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Voir également

* espace de noms [Aspose.Words.Layout](../../aspose.words.layout/)
* Assemblée [Aspose.Words](../../)


