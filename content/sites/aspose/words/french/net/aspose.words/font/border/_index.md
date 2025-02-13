---
title: Font.Border
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Renvoie un objet Border qui spécifie la bordure de la police.
type: docs
weight: 60
url: /fr/net/aspose.words/font/border/
---
## Font.Border property

Renvoie un objet Border qui spécifie la bordure de la police.

```csharp
public Border Border { get; }
```

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

* class [Border](../../border/)
* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


