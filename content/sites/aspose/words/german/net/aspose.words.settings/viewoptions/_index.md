---
title: Class ViewOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Settings.ViewOptions klas. Bietet verschiedene Optionen die steuern wie ein Dokument in Microsoft Word angezeigt wird.
type: docs
weight: 5650
url: /de/net/aspose.words.settings/viewoptions/
---
## ViewOptions class

Bietet verschiedene Optionen, die steuern, wie ein Dokument in Microsoft Word angezeigt wird.

```csharp
public class ViewOptions
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DisplayBackgroundShape](../../aspose.words.settings/viewoptions/displaybackgroundshape/) { get; set; } | Steuert die Anzeige der Hintergrundform in der Drucklayoutansicht. |
| [DoNotDisplayPageBoundaries](../../aspose.words.settings/viewoptions/donotdisplaypageboundaries/) { get; set; } | Deaktiviert die Anzeige des Abstands zwischen dem oberen Rand des Textes und dem oberen Rand der Seite. |
| [FormsDesign](../../aspose.words.settings/viewoptions/formsdesign/) { get; set; } | Gibt an, ob sich das Dokument im Formularentwurfsmodus befindet. |
| [ViewType](../../aspose.words.settings/viewoptions/viewtype/) { get; set; } | Steuert den Ansichtsmodus in Microsoft Word. |
| [ZoomPercent](../../aspose.words.settings/viewoptions/zoompercent/) { get; set; } | Ruft den Prozentsatz (zwischen 10 und 500) ab oder legt ihn fest, mit dem Sie Ihr Dokument anzeigen möchten. |
| [ZoomType](../../aspose.words.settings/viewoptions/zoomtype/) { get; set; } | Ruft einen Zoomwert basierend auf der Größe des Fensters ab oder legt ihn fest. |

### Beispiele

Zeigt, wie Sie einen benutzerdefinierten Zoomfaktor festlegen, der ältere Versionen von Microsoft Word beim Laden auf ein Dokument anwenden.

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

Zeigt, wie Sie einen benutzerdefinierten Zoomtyp festlegen, der ältere Versionen von Microsoft Word beim Laden auf ein Dokument anwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Legen Sie die Eigenschaft "ZoomType" auf "ZoomType.PageWidth" fest, um Microsoft Word zu erhalten
// um das Dokument automatisch an die Breite der Seite anzupassen.
// Legen Sie die Eigenschaft "ZoomType" auf "ZoomType.FullPage" fest, um Microsoft Word zu erhalten
// um das Dokument automatisch zu zoomen, um die gesamte erste Seite sichtbar zu machen.
// Setzen Sie die Eigenschaft "ZoomType" auf "ZoomType.TextFit", um Microsoft Word zu erhalten
// um das Dokument automatisch zu zoomen, um es an die inneren Textränder der ersten Seite anzupassen.
doc.ViewOptions.ZoomType = zoomType;

doc.Save(ArtifactsDir + "ViewOptions.SetZoomType.doc");
```

### Siehe auch

* class [Document](../../aspose.words/document/)
* property [ViewOptions](../../aspose.words/document/viewoptions/)
* namensraum [Aspose.Words.Settings](../../aspose.words.settings/)
* Montage [Aspose.Words](../../)


