---
title: Enum StoryType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.StoryType opsomming. Text eines WordDokuments wird in Storys gespeichert. StoryType identifiziert eine Geschichte.
type: docs
weight: 5820
url: /de/net/aspose.words/storytype/
---
## StoryType enumeration

Text eines Word-Dokuments wird in Storys gespeichert. **StoryType** identifiziert eine Geschichte.

```csharp
public enum StoryType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Standardwert. Es gibt keine solche Geschichte in dem Dokument. |
| MainText | `1` | Enthält den Haupttext des Dokuments, dargestellt durch[`Body`](../body/) . |
| Footnotes | `2` | Enthält Fußnotentext, dargestellt durch[`Footnote`](../../aspose.words.notes/footnote/) . |
| Endnotes | `3` | Enthält Endnotentext, dargestellt durch[`Footnote`](../../aspose.words.notes/footnote/) . |
| Comments | `4` | Enthält Dokumentkommentare (Anmerkungen), dargestellt durch[`Comment`](../comment/) . |
| Textbox | `5` | Enthält Form- oder Textfeldtext, dargestellt durch[`Shape`](../../aspose.words.drawing/shape/) . |
| EvenPagesHeader | `6` | Enthält den Text des Headers der geraden Seiten, dargestellt durch[`HeaderFooter`](../headerfooter/) . |
| PrimaryHeader | `7` | Enthält Text des primären Headers. Wenn der Header für ungerade und gerade Seiten unterschiedlich ist, enthält den Text des Headers der ungeraden Seiten. Vertreten durch[`HeaderFooter`](../headerfooter/) . |
| EvenPagesFooter | `8` | Enthält den Text der Fußzeile der geraden Seite, dargestellt durch[`HeaderFooter`](../headerfooter/) . |
| PrimaryFooter | `9` | Enthält Text der primären Fußzeile. Wenn die Fußzeile für ungerade und gerade Seiten unterschiedlich ist, enthält den Text der Fußzeile der ungeraden Seiten. Vertreten durch[`HeaderFooter`](../headerfooter/) . |
| FirstPageHeader | `10` | Enthält den Text der Kopfzeile der ersten Seite, dargestellt durch[`HeaderFooter`](../headerfooter/) . |
| FirstPageFooter | `11` | Enthält den Text der Fußzeile der ersten Seite, dargestellt durch[`HeaderFooter`](../headerfooter/) . |
| FootnoteSeparator | `12` | Enthält den Text des Fußnotentrennzeichens, dargestellt durchFootnoteSeparator . |
| FootnoteContinuationSeparator | `13` | Enthält den Text des Fußnotenfortsetzungstrennzeichens, dargestellt durchFootnoteSeparator . |
| FootnoteContinuationNotice | `14` | Enthält den Text des Trennzeichens für die Fußnotenfortsetzung, dargestellt durchFootnoteSeparator . |
| EndnoteSeparator | `15` | Enthält den Text des Endnotentrennzeichens, dargestellt durchFootnoteSeparator . |
| EndnoteContinuationSeparator | `16` | Enthält den Text des Endnoten-Fortsetzungstrennzeichens, dargestellt durchFootnoteSeparator . |
| EndnoteContinuationNotice | `17` | Enthält den Text des Trennzeichens für die Endnotenfortsetzung, dargestellt durchFootnoteSeparator . |

### Beispiele

Zeigt, wie alle Shapes von einem Knoten entfernt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Verwenden Sie einen DocumentBuilder, um eine Form einzufügen. Dies ist eine Inline-Form,
// die einen übergeordneten Absatz hat, der ein untergeordneter Knoten des Hauptteils des ersten Abschnitts ist.
builder.InsertShape(ShapeType.Cube, 100.0, 100.0);

Assert.AreEqual(1, doc.GetChildNodes(NodeType.Shape, true).Count);

// Wir können alle Formen aus den untergeordneten Absätzen dieses Körpers löschen.
Assert.AreEqual(StoryType.MainText, doc.FirstSection.Body.StoryType);
doc.FirstSection.Body.DeleteShapes();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Shape, true).Count);
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


