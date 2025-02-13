---
title: Uppdatera fritextkommentar
linktitle: Uppdatera fritextkommentar
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du uppdaterar fritextanteckningsfunktionen i Aspose.PDF för .NET med C#-källkod.
type: docs
weight: 160
url: /sv/net/annotations/updatefreetextannotation/
---
I den här artikeln kommer vi att tillhandahålla en steg-för-steg-guide för att förklara följande C#-källkod för Update Free Text Annotation-funktionen i Aspose.PDF för .NET. Vi kommer att gå igenom varje rad med kod och förklara vad den gör, så att även nybörjare kan förstå den.

Låt oss nu förklara varje rad i koden ovan steg för steg:

## Steg 1: Ställa in dokumentkatalogen

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

På den här raden ställer vi in sökvägen till katalogen som innehåller PDF-dokumentet som vi vill uppdatera.

## Steg 2: Öppna PDF-dokumentet

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

 Här öppnar vi PDF-dokumentet med Aspose.PDF:s`Document` klass och ange sökvägen till indata-PDF-filen.

## Steg 3: Uppdatera teckenstorleken och färgen på fritextkommentaren

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 I det här steget uppdaterar vi teckenstorleken och färgen på den första fritextkommentaren på den andra sidan i PDF-dokumentet. Vi gör detta genom att komma åt`TextStyle` egendom av`FreeTextAnnotation` objekt och ställa in dess`FontSize` och`Color` fastigheter till 18 respektive Green.

## Steg 4: Hantera undantag

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 Detta är en standard`try-catch` block som fångar upp eventuella undantag som kan inträffa när koden körs och skriver ut felmeddelandet till konsolen.

## Slutsats

den här artikeln har vi tillhandahållit en steg-för-steg-guide för att förklara C#-källkoden för funktionen Update Free Text Annotation i Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt uppdatera teckenstorleken och färgen på fritextkommentarer i dina PDF-dokument med Aspose.PDF för .NET.

### Exempel på källkod för Update Free Text Annotation med Aspose.PDF för .NET

Innan vi går in i förklaringen av koden, låt oss först ta en titt på själva koden. Detta kodexempel visar hur man uppdaterar egenskaperna för en fritextkommentar i ett PDF-dokument med Aspose.PDF för .NET.

```csharp
try
{
    // Sökvägen till dokumentkatalogen.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Öppna dokumentet
    Document doc1 = new Document(dataDir + "input.pdf");

    // Ange teckenstorlek och färg på annoteringen:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```