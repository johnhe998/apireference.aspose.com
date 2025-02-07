---
title: Border.LineStyle
second_title: Référence de l'API Aspose.Words pour .NET
description: Border propriété. Obtient ou définit le style de bordure.
type: docs
weight: 40
url: /fr/net/aspose.words/border/linestyle/
---
## Border.LineStyle property

Obtient ou définit le style de bordure.

```csharp
public LineStyle LineStyle { get; set; }
```

### Remarques

Si vous définissez le style de ligne sur aucun, la largeur de ligne est automatiquement modifiée à zéro.

### Exemples

Montre comment insérer une chaîne entourée d'une bordure dans un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### Voir également

* enum [LineStyle](../../linestyle/)
* class [Border](../)
* espace de noms [Aspose.Words](../../border/)
* Assemblée [Aspose.Words](../../../)


