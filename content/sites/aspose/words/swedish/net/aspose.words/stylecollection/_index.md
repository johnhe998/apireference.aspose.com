---
title: Class StyleCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.StyleCollection klass. En samling stilobjekt som representerar både de inbyggda och användardefinierade stilarna i ett dokument.
type: docs
weight: 5840
url: /sv/net/aspose.words/stylecollection/
---
## StyleCollection class

En samling stilobjekt som representerar både de inbyggda och användardefinierade stilarna i ett dokument.

```csharp
public class StyleCollection : IEnumerable<Style>
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/stylecollection/count/) { get; } | Hämtar antalet stilar i samlingen. |
| [DefaultFont](../../aspose.words/stylecollection/defaultfont/) { get; } | Får dokumentets standardtextformatering. |
| [DefaultParagraphFormat](../../aspose.words/stylecollection/defaultparagraphformat/) { get; } | Får dokumentets standardstyckeformatering. |
| [Document](../../aspose.words/stylecollection/document/) { get; } | Hämtar ägardokumentet. |
| [Item](../../aspose.words/stylecollection/item/) { get; } | Får en stil efter namn eller alias. (3 indexers) |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words/stylecollection/add/)(StyleType, string) | Skapar en ny användardefinierad stil och lägger till den i samlingen. |
| [AddCopy](../../aspose.words/stylecollection/addcopy/)(Style) | Kopierar en stil till den här samlingen. |
| [ClearQuickStyleGallery](../../aspose.words/stylecollection/clearquickstylegallery/)() | Tar bort alla stilar från panelen Quick Style Gallery. |
| [GetEnumerator](../../aspose.words/stylecollection/getenumerator/)() | Hämtar ett uppräkningsobjekt som kommer att räkna upp stilar i alfabetisk ordning efter deras namn. |

### Exempel

Visar hur du skapar och använder ett styckeformat med listformatering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en anpassad styckestil.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Skapa en lista och se till att styckena som använder den här stilen kommer att använda den här listan.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Använd styckeformatet på dokumentbyggarens nuvarande stycke och lägg sedan till lite text.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Ändra dokumentbyggarens stil till en som inte har någon listformatering och skriv ett stycke till.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Se även

* class [Style](../style/)
* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


