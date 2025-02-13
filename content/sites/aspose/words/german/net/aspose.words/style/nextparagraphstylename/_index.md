---
title: Style.NextParagraphStyleName
second_title: Aspose.Words für .NET-API-Referenz
description: Style eigendom. Ermittelt/legt den Namen des Stils fest der automatisch auf einen neuen Absatz angewendet werden soll der nach einem Absatz eingefügt wird der mit dem angegebenen Stil formatiert ist.
type: docs
weight: 120
url: /de/net/aspose.words/style/nextparagraphstylename/
---
## Style.NextParagraphStyleName property

Ermittelt/legt den Namen des Stils fest, der automatisch auf einen neuen Absatz angewendet werden soll, der nach einem -Absatz eingefügt wird, der mit dem angegebenen Stil formatiert ist.

```csharp
public string NextParagraphStyleName { get; set; }
```

### Bemerkungen

Diese Eigenschaft wird von Aspose.Words nicht verwendet. Der nächste Absatzstil wird nur automatisch angewendet, wenn Sie das Dokument in MS Word bearbeiten.

### Beispiele

Zeigt, wie auf die Stilsammlung eines Dokuments zugegriffen wird.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Aufzählen und Auflisten aller Stile, die ein mit Aspose.Words erstelltes Dokument standardmäßig enthält.
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

### Siehe auch

* class [Style](../)
* namensraum [Aspose.Words](../../style/)
* Montage [Aspose.Words](../../../)


