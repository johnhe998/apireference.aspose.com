---
title: Enum ViewType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Settings.ViewType opsomming. Mögliche Werte für den Ansichtsmodus in Microsoft Word.
type: docs
weight: 5660
url: /de/net/aspose.words.settings/viewtype/
---
## ViewType enumeration

Mögliche Werte für den Ansichtsmodus in Microsoft Word.

```csharp
public enum ViewType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Das Dokument soll in der Standardansicht der Anwendung gerendert werden. |
| Reading | `0` | Das Dokument soll in der Standardansicht der Anwendung gerendert werden. |
| PageLayout | `1` | Das Dokument soll in einer Ansicht geöffnet werden, die das Dokument so anzeigt, wie es gedruckt wird. |
| Outline | `3` | Das Dokument soll in einer Ansicht gerendert werden, die zum Gliedern oder Erstellen langer Dokumente optimiert ist. |
| Normal | `4` | Das Dokument soll in einer Ansicht gerendert werden, die zum Gliedern oder Erstellen langer Dokumente optimiert ist. |
| Web | `5` | Das Dokument soll in einer Ansicht wiedergegeben werden, die die Art und Weise nachahmt, wie dieses Dokument auf einer Webseite angezeigt würde. |

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

### Siehe auch

* class [ViewOptions](../viewoptions/)
* property [ViewType](../viewoptions/viewtype/)
* namensraum [Aspose.Words.Settings](../../aspose.words.settings/)
* Montage [Aspose.Words](../../)


