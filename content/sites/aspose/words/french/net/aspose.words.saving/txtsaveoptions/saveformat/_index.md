---
title: TxtSaveOptions.SaveFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: TxtSaveOptions propriété. Spécifie le format dans lequel le document sera enregistré si cet objet doptions denregistrement est utilisé. Ne peut êtreText .
type: docs
weight: 60
url: /fr/net/aspose.words.saving/txtsaveoptions/saveformat/
---
## TxtSaveOptions.SaveFormat property

Spécifie le format dans lequel le document sera enregistré si cet objet d'options d'enregistrement est utilisé. Ne peut êtreText .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Exemples

Montre comment enregistrer un document .txt avec un saut de paragraphe personnalisé.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");
builder.Write("Paragraph 3.");

// Crée un objet "TxtSaveOptions", que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont nous enregistrons le document en texte brut.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

Assert.AreEqual(SaveFormat.Text, txtSaveOptions.SaveFormat);

// Définissez le "ParagraphBreak" sur une valeur personnalisée que nous souhaitons mettre à la fin de chaque paragraphe.
txtSaveOptions.ParagraphBreak = " End of paragraph.\n\n\t";

doc.Save(ArtifactsDir + "TxtSaveOptions.ParagraphBreak.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.ParagraphBreak.txt");

Assert.AreEqual("Paragraph 1. End of paragraph.\n\n\t" +
                "Paragraph 2. End of paragraph.\n\n\t" +
                "Paragraph 3. End of paragraph.\n\n\t", docText);
```

### Voir également

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [TxtSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../txtsaveoptions/)
* Assemblée [Aspose.Words](../../../)


