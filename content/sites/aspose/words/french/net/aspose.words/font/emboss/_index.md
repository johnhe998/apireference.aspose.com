---
title: Font.Emboss
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Vrai si la police est formatée en relief.
type: docs
weight: 100
url: /fr/net/aspose.words/font/emboss/
---
## Font.Emboss property

Vrai si la police est formatée en relief.

```csharp
public bool Emboss { get; set; }
```

### Exemples

Montre comment appliquer des effets de gravure/gaufrage au texte.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Color = Color.LightBlue;

// Vous trouverez ci-dessous deux manières d'utiliser les ombres pour appliquer un effet de type 3D au texte.
// 1 - Gravez le texte pour donner l'impression que les lettres sont enfoncées dans la page :
builder.Font.Engrave = true;

builder.Writeln("This text is engraved.");

// 2 - Embossez le texte pour donner l'impression que les lettres sortent de la page :
builder.Font.Engrave = false;
builder.Font.Emboss = true;

builder.Writeln("This text is embossed.");

doc.Save(ArtifactsDir + "Font.EngraveEmboss.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


