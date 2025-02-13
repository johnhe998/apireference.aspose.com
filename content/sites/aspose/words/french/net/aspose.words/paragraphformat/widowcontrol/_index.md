---
title: ParagraphFormat.WidowControl
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Vrai si les première et dernière lignes du paragraphe doivent rester sur la même page que le reste du paragraphe.
type: docs
weight: 390
url: /fr/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Vrai si les première et dernière lignes du paragraphe doivent rester sur la même page que le reste du paragraphe.

```csharp
public bool WidowControl { get; set; }
```

### Exemples

Montre comment activer le contrôle veuve/orphelin pour un paragraphe.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Lorsque nous écrivons le texte qui ne tient pas sur une page, une ligne peut déborder sur la page suivante.
// La ligne unique qui se termine sur la page suivante est appelée "Orphan",
// et la ligne précédente où l'orphelin s'est interrompu s'appelle une "Veuve".
// Nous pouvons corriger les orphelins et les veuves en réorganisant le texte via la taille de la police, l'espacement ou les marges de page.
// Si nous souhaitons conserver les dimensions de notre document, nous pouvons mettre ce drapeau à "true"
 // pour pousser les veuves sur la même page que leurs orphelins respectifs.
// Laisser cet indicateur sur "false" laissera les paires veuve/orpheline dans le texte.
// Chaque paragraphe a ce paramètre accessible dans Microsoft Word via Accueil -> Paragraphe -> Paramètres de paragraphe
// (bouton en bas à droite de l'onglet "Paragraphe") -> "Contrôle des veuves/orphelins".
builder.ParagraphFormat.WidowControl = widowControl; 

// Insère le texte qui produit un orphelin et une veuve.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Voir également

* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


