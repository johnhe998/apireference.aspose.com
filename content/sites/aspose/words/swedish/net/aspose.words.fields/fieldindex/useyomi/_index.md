---
title: FieldIndex.UseYomi
second_title: Aspose.Words för .NET API Referens
description: FieldIndex fast egendom. Hämtar eller ställer in om användningen av yomitext ska aktiveras för indexposter.
type: docs
weight: 170
url: /sv/net/aspose.words.fields/fieldindex/useyomi/
---
## FieldIndex.UseYomi property

Hämtar eller ställer in om användningen av yomi-text ska aktiveras för indexposter.

```csharp
public bool UseYomi { get; set; }
```

### Exempel

Visar hur man sorterar INDEX-fältposter fonetiskt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa ett INDEX-fält som visar en post för varje XE-fält som finns i dokumentet.
// Varje post kommer att visa XE-fältets textegenskapsvärde på vänster sida,
// och numret på sidan som innehåller XE-fältet till höger.
// INDEX-posten samlar alla XE-fält med matchande värden i egenskapen "Text"
// i en post i motsats till att göra en post för varje XE-fält.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// INDEX-tabellen sorterar automatiskt sina poster efter värdena för deras textegenskaper i alfabetisk ordning.
// Ställ in INDEX-tabellen för att sortera poster fonetiskt med Hiragana istället.
index.UseYomi = sortEntriesUsingYomi;

if (sortEntriesUsingYomi)
    Assert.AreEqual(" INDEX  \\y", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX ", index.GetFieldCode());

// Infoga 4 XE-fält, som skulle dyka upp som poster i INDEX-fältets innehållsförteckning.
// Egenskapen "Text" kan innehålla ett ords stavning i Kanji, vars uttal kan vara tvetydigt,
// medan "Yomi"-versionen av ordet stavar exakt hur det uttalas med Hiragana.
// Om vi ställer in vårt INDEX-fält för att använda Yomi, kommer det att sortera dessa poster
// av värdet på deras Yomi-egenskaper istället för deras textvärden.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛子";
indexEntry.Yomi = "あ";

Assert.AreEqual(" XE  愛子 \\y あ", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "明美";
indexEntry.Yomi = "あ";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "恵美";
indexEntry.Yomi = "え";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛美";
indexEntry.Yomi = "え";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Yomi.docx");
```

### Se även

* class [FieldIndex](../)
* namnutrymme [Aspose.Words.Fields](../../fieldindex/)
* hopsättning [Aspose.Words](../../../)


