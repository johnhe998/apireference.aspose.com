---
title: Border.GetHashCode
second_title: Aspose.Words per .NET API Reference
description: Border metodo. Serve come funzione hash per questo tipo.
type: docs
weight: 90
url: /it/net/aspose.words/border/gethashcode/
---
## Border.GetHashCode method

Serve come funzione hash per questo tipo.

```csharp
public override int GetHashCode()
```

### Esempi

Mostra come le raccolte di bordi possono condividere elementi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// Poiché abbiamo utilizzato la stessa configurazione del bordo durante la creazione
// questi paragrafi, le loro raccolte di bordi condividono gli stessi elementi.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;
BorderCollection secondParagraphBorders = builder.CurrentParagraph.ParagraphFormat.Borders;

for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsTrue(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());
    Assert.False(firstParagraphBorders[i].IsVisible);
}

foreach (Border border in secondParagraphBorders)
    border.LineStyle = LineStyle.DotDash;

// Dopo aver modificato lo stile della linea dei bordi solo nel secondo paragrafo,
// le raccolte di bordi non condividono più gli stessi elementi.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // La modifica dell'aspetto di un bordo vuoto lo rende visibile.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### Guarda anche

* class [Border](../)
* spazio dei nomi [Aspose.Words](../../border/)
* assemblea [Aspose.Words](../../../)


