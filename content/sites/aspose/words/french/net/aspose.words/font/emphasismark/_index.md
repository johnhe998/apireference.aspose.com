---
title: Font.EmphasisMark
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Obtient ou définit la marque daccentuation appliquée à cette mise en forme.
type: docs
weight: 110
url: /fr/net/aspose.words/font/emphasismark/
---
## Font.EmphasisMark property

Obtient ou définit la marque d'accentuation appliquée à cette mise en forme.

```csharp
public EmphasisMark EmphasisMark { get; set; }
```

### Exemples

Montre comment ajouter un caractère supplémentaire rendu au-dessus/en dessous du caractère glyphe.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Types possibles de marque d'emphase :
// https://apireference.aspose.com/words/net/aspose.words/emphasismark
builder.Font.EmphasisMark = emphasisMark; 

builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");

builder.Document.Save(ArtifactsDir + "Fonts.SetEmphasisMark.docx");
```

### Voir également

* enum [EmphasisMark](../../emphasismark/)
* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


