---
title: Class ToaCategories
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fields.ToaCategories klas. Repräsentiert eine Tabelle mit Autoritätskategorien.
type: docs
weight: 2600
url: /de/net/aspose.words.fields/toacategories/
---
## ToaCategories class

Repräsentiert eine Tabelle mit Autoritätskategorien.

```csharp
public class ToaCategories
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [ToaCategories](toacategories/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| static [DefaultCategories](../../aspose.words.fields/toacategories/defaultcategories/) { get; } | Ruft das Standardverzeichnis der Autoritätskategorien ab. |
| [Item](../../aspose.words.fields/toacategories/item/) { get; set; } | Ruft die Kategorieüberschrift nach Kategorienummer ab oder legt sie fest. |

### Beispiele

Zeigt, wie ein Satz von Kategorien für TOA-Felder angegeben wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// TOA-Felder können ihre Einträge nach Kategorien filtern, die in dieser Sammlung definiert sind.
ToaCategories toaCategories = new ToaCategories();
doc.FieldOptions.ToaCategories = toaCategories;

// Diese Sammlung von Kategorien enthält Standardwerte, die wir mit benutzerdefinierten Werten überschreiben können.
Assert.AreEqual("Cases", toaCategories[1]);
Assert.AreEqual("Statutes", toaCategories[2]);

toaCategories[1] = "My Category 1";
toaCategories[2] = "My Category 2";

// Über diese Sammlung können wir immer auf die Standardwerte zugreifen.
Assert.AreEqual("Cases", ToaCategories.DefaultCategories[1]);
Assert.AreEqual("Statutes", ToaCategories.DefaultCategories[2]);

// 2 TOA-Felder einfügen. TOA-Felder erstellen einen Eintrag für jedes TA-Feld im Dokument.
// Verwenden Sie den "\c"-Schalter, um den Index einer Kategorie aus unserer Sammlung auszuwählen.
// Mit diesem Schalter nimmt ein TOA-Feld nur Einträge von TA-Feldern auf, die
// haben auch einen "\c"-Schalter mit passendem Kategorieindex. Jedes TOA-Feld wird ebenfalls angezeigt
// der Name der Kategorie, auf die der "\c"-Schalter zeigt.
builder.InsertField("TOA \\c 1 \\h", null);
builder.InsertField("TOA \\c 2 \\h", null);
builder.InsertBreak(BreakType.PageBreak);

// TOA-Einträge in 2 Kategorien einfügen. Unser erstes TOA-Feld erhält einen Eintrag,
// aus dem zweiten TA-Feld, dessen "\c"-Schalter ebenfalls auf die erste Kategorie zeigt.
// Das zweite TOA-Feld enthält zwei Einträge aus den anderen beiden TA-Feldern.
builder.InsertField("TA \\c 2 \\l \"entry 1\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 1 \\l \"entry 2\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 2 \\l \"entry 3\"");

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.TOA.Categories.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Fields](../../aspose.words.fields/)
* Montage [Aspose.Words](../../)


