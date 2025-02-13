---
title: ListFormat.ListIndent
second_title: Aspose.Words för .NET API Referens
description: ListFormat metod. Ökar listnivån för det aktuella stycket med en nivå.
type: docs
weight: 70
url: /sv/net/aspose.words.lists/listformat/listindent/
---
## ListFormat.ListIndent method

Ökar listnivån för det aktuella stycket med en nivå.

```csharp
public void ListIndent()
```

### Anmärkningar

Den här metoden ändrar listnivån och tillämpar formateringsegenskaper för den nya nivån.

I Word-dokument kan listor bestå av upp till nio nivåer. Listformatering för varje nivå anger vilken kula eller nummer som används, vänster indrag, mellanslag mellan kulan och texten etc.

### Exempel

Visar hur man skapar punktlistor och numrerade listor.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Aspose.Words main advantages are:");

// En lista låter oss organisera och dekorera uppsättningar av stycken med prefixsymboler och indrag.
// Vi kan skapa kapslade listor genom att öka indragsnivån. 
// Vi kan börja och avsluta en lista genom att använda en dokumentbyggares "ListFormat"-egenskap. 
// Varje stycke som vi lägger till mellan en listas början och slutet kommer att bli ett objekt i listan.
// Nedan finns två typer av listor som vi kan skapa med en dokumentbyggare.
// 1 - En punktlista:
// Denna lista kommer att tillämpa ett indrag och en punktsymbol ("•") före varje stycke.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Great performance");
builder.Writeln("High reliability");
builder.Writeln("Quality code and working");
builder.Writeln("Wide variety of features");
builder.Writeln("Easy to understand API");

// Avsluta punktlistan.
builder.ListFormat.RemoveNumbers();

builder.InsertBreak(BreakType.ParagraphBreak);
builder.Writeln("Aspose.Words allows:");

// 2 - En numrerad lista:
// Numrerade listor skapar en logisk ordning för sina stycken genom att numrera varje objekt.
builder.ListFormat.ApplyNumberDefault();

// Detta stycke är den första punkten. Den första posten i en numrerad lista kommer att ha en "1". som dess listobjektsymbol.
builder.Writeln("Opening documents from different formats:");

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Anropa metoden "ListIndent" för att öka den aktuella listnivån,
// som kommer att starta en ny fristående lista, med en djupare indrag, vid det aktuella objektet på den första listnivån.
builder.ListFormat.ListIndent();

Assert.AreEqual(1, builder.ListFormat.ListLevelNumber);

// Dessa är de tre första listobjekten på den andra listnivån, som kommer att behålla en räkning
// oberoende av antalet på den första listnivån. Enligt nuvarande listformat,
// de kommer att ha symbolerna "a.", "b." och "c.".
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");

// Anropa metoden "ListOutdent" för att återgå till föregående listnivå.
builder.ListFormat.ListOutdent();

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Dessa två stycken kommer att fortsätta räkningen av den första listnivån.
// Dessa objekt kommer att ha symbolerna "2.", och "3."
builder.Writeln("Processing documents");
builder.Writeln("Saving documents in different formats:");

// Om vi ökar listnivån till en nivå som vi har lagt till objekt till tidigare,
// den kapslade listan kommer att vara separat från den föregående, och dess numrering börjar från början. 
// Dessa listobjekt kommer att ha symbolerna "a.", "b.", "c.", "d." och "e".
builder.ListFormat.ListIndent();
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");
builder.Writeln("MHTML");
builder.Writeln("Plain text");

// Överträffa listnivån igen.
builder.ListFormat.ListOutdent();
builder.Writeln("Doing many other things!");

// Avsluta den numrerade listan.
builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.ApplyDefaultBulletsAndNumbers.docx");
```

### Se även

* class [ListFormat](../)
* namnutrymme [Aspose.Words.Lists](../../listformat/)
* hopsättning [Aspose.Words](../../../)


