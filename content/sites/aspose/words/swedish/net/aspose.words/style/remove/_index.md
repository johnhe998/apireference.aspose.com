---
title: Style.Remove
second_title: Aspose.Words för .NET API Referens
description: Style metod. Tar bort den angivna stilen från dokumentet.
type: docs
weight: 180
url: /sv/net/aspose.words/style/remove/
---
## Style.Remove method

Tar bort den angivna stilen från dokumentet.

```csharp
public void Remove()
```

### Anmärkningar

Formatborttagning har följande effekter på dokumentmodellen:

* Alla referenser till stilen tas bort från motsvarande stycken, körningar och tabeller.
* Om basstilen tas bort flyttas dess formatering till underordnade stilar.
* Om stilen som ska raderas har en länkad stil raderas båda dessa.

### Exempel

Visar hur man skapar och tillämpar en anpassad stil.

```csharp
Document doc = new Document();

Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle");
style.Font.Name = "Times New Roman";
style.Font.Size = 16;
style.Font.Color = Color.Navy;

DocumentBuilder builder = new DocumentBuilder(doc);

// Tillämpa en av stilarna från dokumentet på stycket som dokumentbyggaren skapar.
builder.ParagraphFormat.Style = doc.Styles["MyStyle"];
builder.Writeln("Hello world!");

Style firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

Assert.AreEqual(style, firstParagraphStyle);

// Ta bort vår anpassade stil från dokumentets stilsamling.
doc.Styles["MyStyle"].Remove();

firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

// All text som använde en borttagen stil återgår till standardformateringen.
Assert.False(doc.Styles.Any(s => s.Name == "MyStyle"));
Assert.AreEqual("Times New Roman", firstParagraphStyle.Font.Name);
Assert.AreEqual(12.0d, firstParagraphStyle.Font.Size);
Assert.AreEqual(Color.Empty.ToArgb(), firstParagraphStyle.Font.Color.ToArgb());
```

### Se även

* class [Style](../)
* namnutrymme [Aspose.Words](../../style/)
* hopsättning [Aspose.Words](../../../)


