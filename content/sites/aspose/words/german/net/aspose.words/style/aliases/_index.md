---
title: Style.Aliases
second_title: Aspose.Words für .NET-API-Referenz
description: Style eigendom. Ruft alle Aliase dieses Stils ab. Wenn style keine Aliase hat wird ein leeres StringArray zurückgegeben.
type: docs
weight: 10
url: /de/net/aspose.words/style/aliases/
---
## Style.Aliases property

Ruft alle Aliase dieses Stils ab. Wenn style keine Aliase hat, wird ein leeres String-Array zurückgegeben.

```csharp
public string[] Aliases { get; }
```

### Beispiele

Zeigt, wie Stilaliase verwendet werden.

```csharp
Document doc = new Document(MyDir + "Style with alias.docx");

// Dieses Dokument enthält einen Stil namens "MyStyle,MyStyle Alias 1,MyStyle Alias 2".
// Wenn der Name eines Stils mehrere Werte hat, die durch Kommas getrennt sind, ist jede Klausel ein separater Alias.
Style style = doc.Styles["MyStyle"];
Assert.AreEqual(new [] { "MyStyle Alias 1", "MyStyle Alias 2" }, style.Aliases);
Assert.AreEqual("Title", style.BaseStyleName);
Assert.AreEqual("MyStyle Char", style.LinkedStyleName);

// Wir können auf einen Stil mit seinem Alias und seinem Namen verweisen.
Assert.AreEqual(doc.Styles["MyStyle Alias 1"], doc.Styles["MyStyle Alias 2"]);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 2"];
builder.Write("Hello again!");

Assert.AreEqual(doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.Style, 
    doc.FirstSection.Body.Paragraphs[1].ParagraphFormat.Style);
```

### Siehe auch

* class [Style](../)
* namensraum [Aspose.Words](../../style/)
* Montage [Aspose.Words](../../../)


