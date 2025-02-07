---
title: Class StyleCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.StyleCollection klas. Eine Sammlung von StyleObjekten die sowohl die integrierten als auch die benutzerdefinierten Styles in einem Dokument darstellen.
type: docs
weight: 5840
url: /de/net/aspose.words/stylecollection/
---
## StyleCollection class

Eine Sammlung von Style-Objekten, die sowohl die integrierten als auch die benutzerdefinierten Styles in einem Dokument darstellen.

```csharp
public class StyleCollection : IEnumerable<Style>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words/stylecollection/count/) { get; } | Ruft die Anzahl der Stile in der Sammlung ab. |
| [DefaultFont](../../aspose.words/stylecollection/defaultfont/) { get; } | Ruft die Standardtextformatierung des Dokuments ab. |
| [DefaultParagraphFormat](../../aspose.words/stylecollection/defaultparagraphformat/) { get; } | Ruft die standardmäßige Absatzformatierung des Dokuments ab. |
| [Document](../../aspose.words/stylecollection/document/) { get; } | Ruft das Besitzerdokument ab. |
| [Item](../../aspose.words/stylecollection/item/) { get; } | Ruft einen Stil nach Name oder Alias ab. (3 indexers) |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words/stylecollection/add/)(StyleType, string) | Erstellt einen neuen benutzerdefinierten Stil und fügt ihn der Sammlung hinzu. |
| [AddCopy](../../aspose.words/stylecollection/addcopy/)(Style) | Kopiert einen Stil in diese Sammlung. |
| [ClearQuickStyleGallery](../../aspose.words/stylecollection/clearquickstylegallery/)() | Entfernt alle Stile aus dem Schnellstil-Galeriebedienfeld. |
| [GetEnumerator](../../aspose.words/stylecollection/getenumerator/)() | Ruft ein Aufzählungsobjekt ab, das Stile in der alphabetischen Reihenfolge ihrer Namen auflistet. |

### Beispiele

Zeigt, wie Sie ein Absatzformat mit Listenformatierung erstellen und verwenden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einen benutzerdefinierten Absatzstil erstellen.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Erstellen Sie eine Liste und stellen Sie sicher, dass die Absätze, die diesen Stil verwenden, diese Liste verwenden.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Den Absatzstil auf den aktuellen Absatz des Document Builder anwenden und dann etwas Text hinzufügen.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Ändern Sie den Stil des Document Builder in einen Stil ohne Listenformatierung und schreiben Sie einen weiteren Absatz.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Siehe auch

* class [Style](../style/)
* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


