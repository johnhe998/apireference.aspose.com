---
title: Style.Name
second_title: Aspose.Words für .NET-API-Referenz
description: Style eigendom. Ruft den Namen des Stils ab oder legt ihn fest.
type: docs
weight: 110
url: /de/net/aspose.words/style/name/
---
## Style.Name property

Ruft den Namen des Stils ab oder legt ihn fest.

```csharp
public string Name { get; set; }
```

### Bemerkungen

Darf keine leere Zeichenfolge sein.

Wenn es bereits einen Stil mit einem solchen Namen in der Sammlung gibt, wird dieser Stil ihn überschreiben. Alle betroffenen Knoten verweisen auf den neuen Stil.

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

Zeigt, wie Sie den Stil eines Dokuments klonen.

```csharp
Document doc = new Document();

// Die AddCopy-Methode erstellt eine Kopie des angegebenen Stils und
// generiert automatisch einen neuen Namen für den Stil, z. B. "Überschrift 1_0".
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// Verwenden Sie die "Name"-Eigenschaft des Stils, um den identifizierenden Namen des Stils zu ändern.
newStyle.Name = "My Heading 1";

// Unser Dokument hat jetzt zwei identisch aussehende Stile mit unterschiedlichen Namen.
// Das Ändern der Einstellungen eines der Stile wirkt sich nicht auf den anderen aus.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### Siehe auch

* class [Style](../)
* namensraum [Aspose.Words](../../style/)
* Montage [Aspose.Words](../../../)


