---
title: Class LayoutOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Layout.LayoutOptions klas. Enthält die Optionen mit denen der Dokumentlayoutprozess gesteuert werden kann.
type: docs
weight: 3150
url: /de/net/aspose.words.layout/layoutoptions/
---
## LayoutOptions class

Enthält die Optionen, mit denen der Dokumentlayoutprozess gesteuert werden kann.

```csharp
public class LayoutOptions
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [LayoutOptions](layoutoptions/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Callback](../../aspose.words.layout/layoutoptions/callback/) { get; set; } | Holt oder setzt[`IPageLayoutCallback`](../ipagelayoutcallback/)Implementierung, die vom Seitenlayoutmodell verwendet wird. |
| [CommentDisplayMode](../../aspose.words.layout/layoutoptions/commentdisplaymode/) { get; set; } | Ruft ab oder legt fest, wie Kommentare gerendert werden. Der Standardwert istShowInBalloons . |
| [ContinuousSectionPageNumberingRestart](../../aspose.words.layout/layoutoptions/continuoussectionpagenumberingrestart/) { get; set; } | Ruft den Verhaltensmodus für die Berechnung von Seitenzahlen ab oder legt ihn fest, wenn ein fortlaufender Abschnitt die Seitennummerierung neu startet. |
| [IgnorePrinterMetrics](../../aspose.words.layout/layoutoptions/ignoreprintermetrics/) { get; set; } | Ruft ab oder legt fest, ob die Kompatibilitätsoption „Druckermaße zum Layout des Dokuments verwenden“ ignoriert wird. Standard ist True. |
| [RevisionOptions](../../aspose.words.layout/layoutoptions/revisionoptions/) { get; } | Ruft Revisionsoptionen ab. |
| [ShowHiddenText](../../aspose.words.layout/layoutoptions/showhiddentext/) { get; set; } | Ruft ab oder legt fest, ob verborgener Text im Dokument gerendert wird. Standard ist False. |
| [ShowParagraphMarks](../../aspose.words.layout/layoutoptions/showparagraphmarks/) { get; set; } | Ruft ab oder legt fest, ob Absatzmarken gerendert werden. Standard ist False. |
| [TextShaperFactory](../../aspose.words.layout/layoutoptions/textshaperfactory/) { get; set; } | Holt oder setzt[`ITextShaperFactory`](../../aspose.words.shaping/itextshaperfactory/) Implementierung, die für erweiterte Typografie-Rendering-Funktionen verwendet wird. |

### Bemerkungen

Sie erstellen keine Instanzen dieser Klasse direkt. Verwenden Sie die[`LayoutOptions`](../../aspose.words/document/layoutoptions/)-Eigenschaft, um auf Layoutoptionen für dieses Dokument zuzugreifen.

Beachten Sie, dass nach dem Ändern einer der in dieser Klasse vorhandenen Optionen[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) method sollte aufgerufen werden, damit die geänderten Optionen auf das Layout angewendet werden.

### Beispiele

Zeigt, wie Text in einem gerenderten Ausgabedokument ausgeblendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Verborgenen Text einfügen, dann angeben, ob wir ihn aus einem gerenderten Dokument weglassen möchten.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

Zeigt, wie Absatzmarken in einem gerenderten Ausgabedokument angezeigt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Einige Absätze hinzufügen, dann Absatzmarken aktivieren, um die Enden der Absätze anzuzeigen
// mit einem Pilcrow (¶)-Symbol, wenn wir das Dokument rendern.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

Zeigt, wie das Erscheinungsbild von Revisionen in einem gerenderten Ausgabedokument geändert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Revision einfügen, dann die Farbe aller Revisionen auf Grün ändern.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Entfernen Sie den Balken, der links von jeder überarbeiteten Zeile erscheint.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Siehe auch

* namensraum [Aspose.Words.Layout](../../aspose.words.layout/)
* Montage [Aspose.Words](../../)


