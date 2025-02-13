---
title: Font.Italic
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Vrai si la police est formatée en italique.
type: docs
weight: 160
url: /fr/net/aspose.words/font/italic/
---
## Font.Italic property

Vrai si la police est formatée en italique.

```csharp
public bool Italic { get; set; }
```

### Exemples

Montre comment écrire du texte en italique à l'aide d'un générateur de document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Italic = true;
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "Font.Italic.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


