---
title: Document.ViewOptions
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Ger alternativ för att styra hur dokumentet visas i Microsoft Word.
type: docs
weight: 450
url: /sv/net/aspose.words/document/viewoptions/
---
## Document.ViewOptions property

Ger alternativ för att styra hur dokumentet visas i Microsoft Word.

```csharp
public ViewOptions ViewOptions { get; }
```

### Exempel

Visar hur man ställer in en anpassad zoomfaktor, vilken äldre versioner av Microsoft Word kommer att tillämpa på ett dokument vid inläsning.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

Visar hur man ställer in en anpassad zoomtyp, vilka äldre versioner av Microsoft Word som kommer att tillämpas på ett dokument vid inläsning.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Ställ in "ZoomType"-egenskapen till "ZoomType.PageWidth" för att hämta Microsoft Word
// för att automatiskt zooma dokumentet så att det passar sidans bredd.
// Ställ in "ZoomType"-egenskapen till "ZoomType.FullPage" för att hämta Microsoft Word
// för att automatiskt zooma dokumentet för att göra hela första sidan synlig.
// Ställ in "ZoomType"-egenskapen till "ZoomType.TextFit" för att hämta Microsoft Word
// för att automatiskt zooma dokumentet så att det passar de inre textmarginalerna på första sidan.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Se även

* class [ViewOptions](../../../aspose.words.settings/viewoptions/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


