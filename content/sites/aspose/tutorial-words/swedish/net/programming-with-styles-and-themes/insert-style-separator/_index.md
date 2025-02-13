---
title: Sätt in stilavskiljare
linktitle: Sätt in stilavskiljare
second_title: Aspose.Words för .NET API Referens
description: Lär dig att skapa dokument med anpassade stilar och infoga stilavgränsare för exakt, professionell formatering.
type: docs
weight: 10
url: /sv/net/programming-with-styles-and-themes/insert-style-separator/
---
I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för att infoga en stilavgränsare i ett dokument med Aspose.Words för .NET. Vi kommer att skapa ett nytt dokument, definiera anpassade stilar och infoga en stilavgränsare.

## Steg 1: Sätta upp miljön

Se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Skapa ett nytt dokumentobjekt

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 I det här steget skapar vi en ny`Document` objekt och en tillhörande`DocumentBuilder` objekt.

## Steg 3: Skapa och konfigurera den anpassade stilen

```csharp
Style paraStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyParaStyle");
paraStyle.Font.Bold = false;
paraStyle.Font.Size = 8;
paraStyle.Font.Name = "Arial";
```

I det här steget skapar vi en anpassad styckestil med namnet "MyParaStyle" och ställer in dess teckensnittsegenskaper.

## Steg 4: Infoga stilavgränsaren

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Heading 1");
builder. InsertStyleSeparator();
builder.ParagraphFormat.StyleName = paraStyle.Name;
builder.Write("This is text with some other formatting");
```

I det här steget ställer vi in styckestilen till "Rubrik 1", skriver lite text med den här stilen och infogar sedan en stilavgränsare. Sedan ställer vi in styckestilen till vår anpassade stil "MyParaStyle" och skriver lite text med denna stil.

## Steg 5: Spara dokumentet

I det här sista steget kan du spara det skapade dokumentet efter dina behov.

Du kan köra källkod för att infoga en stilavgränsare i ett dokument. Detta låter dig skapa textavsnitt med olika stilar och anpassa utseendet på ditt dokument.

### Exempel på källkod för Insert Style Separator med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Style paraStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyParaStyle");
paraStyle.Font.Bold = false;
paraStyle.Font.Size = 8;
paraStyle.Font.Name = "Arial";

// Lägg till text med stilen "Rubrik 1".
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Heading 1");
builder.InsertStyleSeparator();

// Lägg till text med en annan stil.
builder.ParagraphFormat.StyleName = paraStyle.Name;
builder.Write("This is text with some other formatting ");

doc.Save(dataDir + "WorkingWithStylesAndThemes.InsertStyleSeparator.docx");
            
        
```

## Slutsats

den här handledningen lärde vi oss hur man infogar en stilavgränsare i ett dokument med Aspose.Words för .NET. Vi skapade ett nytt dokument, definierade en anpassad stil och använde stilavgränsaren för att skilja textavsnitt med olika stilar.

Att använda stilavgränsare ger ytterligare flexibilitet när du formaterar dina dokument. Detta hjälper till att upprätthålla visuell konsistens samtidigt som det tillåter stilistisk variation.

Aspose.Words för .NET tillhandahåller ett kraftfullt API för att hantera stilar i dina dokument. Du kan utforska det här biblioteket ytterligare för att anpassa utseendet på dina dokument och skapa professionella resultat.

Kom ihåg att spara ditt dokument efter att du har infogat stilavgränsaren.