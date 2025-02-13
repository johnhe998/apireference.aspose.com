---
title: Font.UnderlineColor
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Obtient ou définit la couleur du soulignement appliqué à la police.
type: docs
weight: 540
url: /fr/net/aspose.words/font/underlinecolor/
---
## Font.UnderlineColor property

Obtient ou définit la couleur du soulignement appliqué à la police.

```csharp
public Color UnderlineColor { get; set; }
```

### Exemples

Montre comment configurer le style et la couleur d'un texte souligné.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Underline = Underline.Dotted;
builder.Font.UnderlineColor = Color.Red;

builder.Writeln("Underlined text.");

doc.Save(ArtifactsDir + "Font.Underlines.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


