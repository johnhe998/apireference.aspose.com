---
title: Class FieldNumChars
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fields.FieldNumChars klass. Implementerar fältet NUMCHARS.
type: docs
weight: 2060
url: /sv/net/aspose.words.fields/fieldnumchars/
---
## FieldNumChars class

Implementerar fältet NUMCHARS.

```csharp
public class FieldNumChars : Field
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [FieldNumChars](fieldnumchars/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Hämtar texten som representerar det visade fältresultatet. |
| [End](../../aspose.words.fields/field/end/) { get; } | Hämtar noden som representerar fältänden. |
| [Format](../../aspose.words.fields/field/format/) { get; } | Får en[`FieldFormat`](../fieldformat/) objekt som ger maskinskriven åtkomst till fältets formatering. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Hämtar eller ställer in om det aktuella resultatet av fältet inte längre är korrekt (inaktuellt) på grund av andra ändringar som gjorts i dokumentet. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Hämtar eller ställer in om fältet är låst (ska inte räkna om resultatet). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Hämtar eller ställer in LCID för fältet. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Hämtar eller ställer in text som är mellan fältavgränsaren och fältslutet. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Hämtar noden som representerar fältseparatorn. Kan vara null. |
| [Start](../../aspose.words.fields/field/start/) { get; } | Hämtar noden som representerar början av fältet. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | Hämtar fälttypen Microsoft Word. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | Returnerar text mellan fältstart och fältavgränsare (eller fältslut om det inte finns någon avgränsare). Både fältkod och fältresultat för underordnade fält ingår. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | Returnerar text mellan fältstart och fältavgränsare (eller fältslut om det inte finns någon avgränsare). |
| [Remove](../../aspose.words.fields/field/remove/)() | Tar bort fältet från dokumentet. Returnerar en nod direkt efter fältet. Om fältets slut är den sista child av dess överordnade nod, returnerar dess överordnade stycke. Om fältet redan är borttaget, returneras **null** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | Utför fältavlänkningen. |
| [Update](../../aspose.words.fields/field/update/)() | Utför fältuppdateringen. Kastar om fältet redan uppdateras. |
| [Update](../../aspose.words.fields/field/update/)(bool) | Utför en fältuppdatering. Kastar om fältet redan uppdateras. |

### Anmärkningar

Hämtar antalet tecken i det aktuella dokumentet, som registrerats i **Tecken**egenskapen för inbyggda dokumentegenskaper.

### Exempel

Visar hur du använder NUMCHARS, NUMWORDS, NUMPAGES och PAGE-fälten för att spåra storleken på våra dokument.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

// Nedan finns tre typer av fält som vi kan använda för att spåra storleken på våra dokument.
// 1 - Spåra teckenantalet med ett NUMCHARS-fält:
FieldNumChars fieldNumChars = (FieldNumChars)builder.InsertField(FieldType.FieldNumChars, true);       
builder.Writeln(" characters");

// 2 - Spåra ordantalet med ett NUMWORDS-fält:
FieldNumWords fieldNumWords = (FieldNumWords)builder.InsertField(FieldType.FieldNumWords, true);
builder.Writeln(" words");

// 3 - Använd både PAGE- och NUMPAGES-fälten för att visa vilken sida fältet är på,
// och det totala antalet sidor i dokumentet:
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Page ");
FieldPage fieldPage = (FieldPage)builder.InsertField(FieldType.FieldPage, true);
builder.Write(" of ");
FieldNumPages fieldNumPages = (FieldNumPages)builder.InsertField(FieldType.FieldNumPages, true);

Assert.AreEqual(" NUMCHARS ", fieldNumChars.GetFieldCode());
Assert.AreEqual(" NUMWORDS ", fieldNumWords.GetFieldCode());
Assert.AreEqual(" NUMPAGES ", fieldNumPages.GetFieldCode());
Assert.AreEqual(" PAGE ", fieldPage.GetFieldCode());

// Dessa fält kommer inte att bibehålla korrekta värden i realtid
// medan vi redigerar dokumentet programmatiskt med Aspose.Words eller i Microsoft Word.
  // Vi måste uppdatera dem varje gång vi behöver för att se ett aktuellt värde.
doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.NUMCHARS.NUMWORDS.NUMPAGES.PAGE.docx");
```

### Se även

* class [Field](../field/)
* namnutrymme [Aspose.Words.Fields](../../aspose.words.fields/)
* hopsättning [Aspose.Words](../../)


