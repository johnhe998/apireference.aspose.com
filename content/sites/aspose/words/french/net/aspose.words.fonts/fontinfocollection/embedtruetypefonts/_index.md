---
title: FontInfoCollection.EmbedTrueTypeFonts
second_title: Référence de l'API Aspose.Words pour .NET
description: FontInfoCollection propriété. Spécifie sil faut ou non incorporer des polices TrueType dans un document lors de son enregistrement. La valeur par défaut de cette propriété est faux .
type: docs
weight: 30
url: /fr/net/aspose.words.fonts/fontinfocollection/embedtruetypefonts/
---
## FontInfoCollection.EmbedTrueTypeFonts property

Spécifie s'il faut ou non incorporer des polices TrueType dans un document lors de son enregistrement. La valeur par défaut de cette propriété est **faux** .

```csharp
public bool EmbedTrueTypeFonts { get; set; }
```

### Remarques

L'incorporation de polices TrueType permet aux autres de visualiser le document avec les mêmes polices que celles utilisées pour le créer, mais peut augmenter considérablement la taille du document.

Cette option fonctionne uniquement pour les formats DOC, DOCX et RTF.

### Exemples

Montre comment enregistrer un document avec des polices TrueType intégrées.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Voir également

* class [FontInfoCollection](../)
* espace de noms [Aspose.Words.Fonts](../../fontinfocollection/)
* Assemblée [Aspose.Words](../../../)


