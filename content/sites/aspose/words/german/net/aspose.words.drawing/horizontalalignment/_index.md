---
title: Enum HorizontalAlignment
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.HorizontalAlignment opsomming. Gibt die horizontale Ausrichtung einer schwebenden Form eines Textrahmens oder einer schwebenden Tabelle an.
type: docs
weight: 900
url: /de/net/aspose.words.drawing/horizontalalignment/
---
## HorizontalAlignment enumeration

Gibt die horizontale Ausrichtung einer schwebenden Form, eines Textrahmens oder einer schwebenden Tabelle an.

```csharp
public enum HorizontalAlignment
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Das Objekt wird explizit positioniert, normalerweise mit seinem **Links** Eigentum. |
| Default | `0` | Gleich wieNone . |
| Left | `1` | Gibt an, dass das Objekt linksbündig an der horizontalen Ausrichtungsbasis ausgerichtet werden soll. |
| Center | `2` | Gibt an, dass das Objekt in Bezug auf die horizontale Ausrichtungsbasis zentriert werden soll. |
| Right | `3` | Gibt an, dass das Objekt rechts an der horizontalen Ausrichtungsbasis ausgerichtet werden soll. |
| Inside | `4` | Gibt an, dass sich das Objekt innerhalb der horizontalen Ausrichtungsbasis befinden soll. |
| Outside | `5` | Gibt an, dass sich das Objekt außerhalb der horizontalen Ausrichtungsbasis befinden soll. |

### Beispiele

Zeigt, wie ein schwebendes Bild in der Mitte einer Seite eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein, das hinter dem überlappenden Text angezeigt wird, und richten Sie es an der Mitte der Seite aus.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Siehe auch

* property [HorizontalAlignment](../shapebase/horizontalalignment/)
* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


