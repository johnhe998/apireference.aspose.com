---
title: Class FieldAutoNumOut
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fields.FieldAutoNumOut klass. Implementerar fältet AUTONUMOUT.
type: docs
weight: 1450
url: /sv/net/aspose.words.fields/fieldautonumout/
---
## FieldAutoNumOut class

Implementerar fältet AUTONUMOUT.

```csharp
public class FieldAutoNumOut : Field
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [FieldAutoNumOut](fieldautonumout/)() | Default_Constructor |

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

Infogar ett automatiskt nummer i konturformat.

### Exempel

Visar hur man numrerar stycken med AUTONUMOUT-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// AUTONUMOUT-fält visar ett tal som ökar vid varje AUTONUMOUT-fält.
// Till skillnad från AUTONUM-fält använder AUTONUMOUT-fält konturnumreringsschemat,
// som vi kan definiera i Microsoft Word via Format -> Kulor & Numrering -> "Kontur numrerad".
// Detta tillåter oss att automatiskt numrera objekt som en numrerad lista.
// LISTNUM-fält är ett nyare alternativ till AUTONUMOUT-fält.
// Detta fält kommer att visa "1.".
builder.InsertField(FieldType.FieldAutoNumOutline, true);
builder.Writeln("\tParagraph 1.");

// Detta fält kommer att visa "2.".
builder.InsertField(FieldType.FieldAutoNumOutline, true);
builder.Writeln("\tParagraph 2.");

foreach (FieldAutoNumOut field in doc.Range.Fields.Where(f => f.Type == FieldType.FieldAutoNumOutline))
    Assert.AreEqual(" AUTONUMOUT ", field.GetFieldCode());

doc.Save(ArtifactsDir + "Field.AUTONUMOUT.docx");
```

### Se även

* class [Field](../field/)
* namnutrymme [Aspose.Words.Fields](../../aspose.words.fields/)
* hopsättning [Aspose.Words](../../)


