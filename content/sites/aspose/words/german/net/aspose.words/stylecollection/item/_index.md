---
title: StyleCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: StyleCollection eigendom. Ruft einen Stil nach Name oder Alias ab.
type: docs
weight: 50
url: /de/net/aspose.words/stylecollection/item/
---
## StyleCollection indexer (1 of 3)

Ruft einen Stil nach Name oder Alias ab.

```csharp
public Style this[string name] { get; }
```

### Bemerkungen

Groß-/Kleinschreibung beachten, gibt null zurück, wenn der Stil mit dem angegebenen Namen nicht gefunden wird.

Wenn dies ein englischer Name eines eingebauten Stils ist, der noch nicht existiert, wird dieser automatisch erstellt.

### Beispiele

Zeigt an, wann das Seitenlayout des Dokuments neu berechnet werden soll.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Das Speichern eines Dokuments als PDF, in ein Bild oder das erstmalige Drucken erfolgt automatisch
// das Layout des Dokuments innerhalb seiner Seiten zwischenspeichern.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// Ändern Sie das Dokument auf irgendeine Weise.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // In der aktuellen Version von Aspose.Words wird das Dokument nicht automatisch neu erstellt, wenn es geändert wird
// das zwischengespeicherte Seitenlayout. Wenn wir das zwischengespeicherte Layout wünschen
// Um auf dem neuesten Stand zu bleiben, müssen wir es manuell aktualisieren.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### Siehe auch

* class [Style](../../style/)
* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)

---

## StyleCollection indexer (2 of 3)

Ruft einen eingebauten Stil durch seine Gebietsschema-unabhängige Kennung ab.

```csharp
public Style this[StyleIdentifier sti] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| sti | EIN[`StyleIdentifier`](../../styleidentifier/) -Wert, der den abzurufenden integrierten Stil angibt. |

### Bemerkungen

Beim Zugriff auf einen noch nicht vorhandenen Stil wird dieser automatisch erstellt.

### Beispiele

Zeigt, wie Sie der Stilsammlung eines Dokuments einen Stil hinzufügen.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Legen Sie Standardparameter für neue Stile fest, die wir später zu dieser Sammlung hinzufügen können.
styles.DefaultFont.Name = "Courier New";

// Wenn wir einen Stil des "StyleType.Paragraph" hinzufügen, wendet die Sammlung die Werte von an
// seine "DefaultParagraphFormat"-Eigenschaft auf die "ParagraphFormat"-Eigenschaft des Stils.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Füge einen Stil hinzu und vergewissere dich, dass er die Standardeinstellungen hat.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Siehe auch

* class [Style](../../style/)
* enum [StyleIdentifier](../../styleidentifier/)
* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)

---

## StyleCollection indexer (3 of 3)

Ruft einen Stil nach Index ab.

```csharp
public Style this[int index] { get; }
```

### Beispiele

Zeigt, wie Sie der Stilsammlung eines Dokuments einen Stil hinzufügen.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Legen Sie Standardparameter für neue Stile fest, die wir später zu dieser Sammlung hinzufügen können.
styles.DefaultFont.Name = "Courier New";

// Wenn wir einen Stil des "StyleType.Paragraph" hinzufügen, wendet die Sammlung die Werte von an
// seine "DefaultParagraphFormat"-Eigenschaft auf die "ParagraphFormat"-Eigenschaft des Stils.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Füge einen Stil hinzu und vergewissere dich, dass er die Standardeinstellungen hat.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Siehe auch

* class [Style](../../style/)
* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)


