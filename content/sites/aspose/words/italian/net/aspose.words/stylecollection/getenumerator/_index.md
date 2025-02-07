---
title: StyleCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: StyleCollection metodo. Ottiene un oggetto enumeratore che enumera gli stili nellordine alfabetico dei loro nomi.
type: docs
weight: 90
url: /it/net/aspose.words/stylecollection/getenumerator/
---
## StyleCollection.GetEnumerator method

Ottiene un oggetto enumeratore che enumera gli stili nell'ordine alfabetico dei loro nomi.

```csharp
public IEnumerator<Style> GetEnumerator()
```

### Esempi

Mostra come accedere alla raccolta di stili di un documento.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Enumera ed elenca tutti gli stili che un documento creato utilizzando Aspose.Words contiene per impostazione predefinita.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

### Guarda anche

* class [Style](../../style/)
* class [StyleCollection](../)
* spazio dei nomi [Aspose.Words](../../stylecollection/)
* assemblea [Aspose.Words](../../../)


