---
title: HtmlSaveOptions.DocumentSplitHeadingLevel
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt die maximale Überschriftenebene an bei der das Dokument geteilt werden soll. Der Standardwert ist2 .
type: docs
weight: 90
url: /de/net/aspose.words.saving/htmlsaveoptions/documentsplitheadinglevel/
---
## HtmlSaveOptions.DocumentSplitHeadingLevel property

Gibt die maximale Überschriftenebene an, bei der das Dokument geteilt werden soll. Der Standardwert ist`2` .

```csharp
public int DocumentSplitHeadingLevel { get; set; }
```

### Bemerkungen

Wann[`DocumentSplitCriteria`](../documentsplitcriteria/) beinhaltetHeadingParagraph und diese Eigenschaft auf einen Wert von 1 bis 9 gesetzt ist, wird das Dokument an Absätzen geteilt, die mit formatiert sind. **Überschrift 1** , **Überschrift 2** , **Überschrift 3** usw. Stile bis zur angegebenen Überschriftenebene.

Nur standardmäßig **Überschrift 1** und **Überschrift 2** Absätze führen dazu, dass das Dokument geteilt wird. Wenn Sie diese Eigenschaft auf Null setzen, wird das Dokument überhaupt nicht an den Überschriftenabsätzen geteilt.

### Beispiele

Zeigt, wie ein ausgegebenes HTML-Dokument anhand von Überschriften in mehrere Teile aufgeteilt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Jeder Absatz, den wir mit einem "Überschrift"-Stil formatieren, kann als Überschrift dienen.
// Jede Überschrift kann auch eine Überschriftenebene haben, die durch die Nummer ihres Überschriftenstils bestimmt wird.
// Die folgenden Überschriften gehören zu den Ebenen 1-3.
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 1"];
builder.Writeln("Heading #1");
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 2"];
builder.Writeln("Heading #2");
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("Heading #3");
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 1"];
builder.Writeln("Heading #4");
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 2"];
builder.Writeln("Heading #5");
builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("Heading #6");

// Erstellen Sie ein HtmlSaveOptions-Objekt und setzen Sie die Aufteilungskriterien auf "HeadingParagraph".
// Diese Kriterien teilen das Dokument an Absätzen mit "Überschrift"-Stilen in mehrere kleinere Dokumente auf,
// und speichern Sie jedes Dokument in einer separaten HTML-Datei im lokalen Dateisystem.
// Wir werden auch die maximale Überschriftenebene festlegen, die das Dokument auf 2 aufteilt.
// Beim Speichern des Dokuments wird es an den Überschriften der Ebenen 1 und 2 geteilt, aber nicht an den Ebenen 3 bis 9.
HtmlSaveOptions options = new HtmlSaveOptions
{
    DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph,
    DocumentSplitHeadingLevel = 2
};

// Unser Dokument hat vier Überschriften der Ebenen 1 - 2. Eine dieser Überschriften wird es nicht sein
// ein Teilungspunkt, da er sich am Anfang des Dokuments befindet.
// Die Speicheroperation wird unser Dokument an drei Stellen in vier kleinere Dokumente aufteilen.
doc.Save(ArtifactsDir + "HtmlSaveOptions.HeadingLevels.html", options);

doc = new Document(ArtifactsDir + "HtmlSaveOptions.HeadingLevels.html");

Assert.AreEqual("Heading #1", doc.GetText().Trim());

doc = new Document(ArtifactsDir + "HtmlSaveOptions.HeadingLevels-01.html");

Assert.AreEqual("Heading #2\r" +
                "Heading #3", doc.GetText().Trim());

doc = new Document(ArtifactsDir + "HtmlSaveOptions.HeadingLevels-02.html");

Assert.AreEqual("Heading #4", doc.GetText().Trim());

doc = new Document(ArtifactsDir + "HtmlSaveOptions.HeadingLevels-03.html");

Assert.AreEqual("Heading #5\r" +
                "Heading #6", doc.GetText().Trim());
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


