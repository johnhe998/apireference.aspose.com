---
title: FieldOptions.UseInvariantCultureNumberFormat
second_title: Aspose.Words för .NET API Referens
description: FieldOptions fast egendom. Hämtar eller ställer in värdet som indikerar att talformatet tolkas med invariant kultur eller inte
type: docs
weight: 190
url: /sv/net/aspose.words.fields/fieldoptions/useinvariantculturenumberformat/
---
## FieldOptions.UseInvariantCultureNumberFormat property

Hämtar eller ställer in värdet som indikerar att talformatet tolkas med invariant kultur eller inte

```csharp
public bool UseInvariantCultureNumberFormat { get; set; }
```

### Anmärkningar

När den här egenskapen är inställd på **Sann** , talformatet är hämtat från en invariant kultur.

När den här egenskapen är inställd på **falsk** nummerformatet är hämtat från den aktuella trådens kultur.

Standardvärdet är **falsk**.

### Exempel

Visar hur man formaterar tal enligt den invarianta kulturen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
Field field = builder.InsertField(" = 1234567,89 \\# $#,###,###.##");
field.Update();

// Ibland kanske fält inte formaterar sina nummer korrekt under vissa kulturer. 
Assert.IsFalse(doc.FieldOptions.UseInvariantCultureNumberFormat);
Assert.AreEqual("$1234567,89 .     ", field.Result);

// För att fixa detta kan vi ändra kulturen för hela tråden.
// Ett annat sätt att fixa detta är att ställa in denna flagga,
// som får alla fält att använda den invarianta kulturen vid formatering av tal.
// På detta sätt kan vi undvika att förändra kulturen för hela tråden.
doc.FieldOptions.UseInvariantCultureNumberFormat = true;
field.Update();
Assert.AreEqual("$1.234.567,89", field.Result);
```

### Se även

* class [FieldOptions](../)
* namnutrymme [Aspose.Words.Fields](../../fieldoptions/)
* hopsättning [Aspose.Words](../../../)


