---
title: Font.LineSpacing
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Renvoie linterligne de cette police en points.
type: docs
weight: 190
url: /fr/net/aspose.words/font/linespacing/
---
## Font.LineSpacing property

Renvoie l'interligne de cette police (en points).

```csharp
public double LineSpacing { get; }
```

### Exemples

Montre comment obtenir l'interligne d'une police, en points.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Définir différentes polices pour le DocumentBuilder et vérifier leur interligne.
builder.Font.Name = "Calibri";
Assert.AreEqual(14.6484375d, builder.Font.LineSpacing);

builder.Font.Name = "Times New Roman";
Assert.AreEqual(13.798828125d, builder.Font.LineSpacing);
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


