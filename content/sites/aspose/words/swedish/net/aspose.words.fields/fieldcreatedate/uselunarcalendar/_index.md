---
title: FieldCreateDate.UseLunarCalendar
second_title: Aspose.Words för .NET API Referens
description: FieldCreateDate fast egendom. Hämtar eller ställer in om du vill använda Hijri Lunar eller Hebrew Lunar kalender.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldcreatedate/uselunarcalendar/
---
## FieldCreateDate.UseLunarCalendar property

Hämtar eller ställer in om du vill använda Hijri Lunar eller Hebrew Lunar kalender.

```csharp
public bool UseLunarCalendar { get; set; }
```

### Exempel

Visar hur du använder fältet CREATEDATE för att visa datum/tid för dokumentet.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln(" Date this document was created:");

// Vi kan använda fältet CREATEDATE för att visa datum och tid då dokumentet skapades.
// Nedan finns tre olika kalendertyper enligt vilka fältet CREATEDATE kan visa datum/tid.
// 1 - Islamisk månkalender:
builder.Write("According to the Lunar Calendar - ");
FieldCreateDate field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseLunarCalendar = true;

Assert.AreEqual(" CREATEDATE  \\h", field.GetFieldCode());

// 2 - Umm al-Qura kalender:
builder.Write("\nAccording to the Umm al-Qura Calendar - ");
field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseUmAlQuraCalendar = true;

Assert.AreEqual(" CREATEDATE  \\u", field.GetFieldCode());

// 3 - Indian National Calendar:
builder.Write("\nAccording to the Indian National Calendar - ");
field = (FieldCreateDate)builder.InsertField(FieldType.FieldCreateDate, true);
field.UseSakaEraCalendar = true;

Assert.AreEqual(" CREATEDATE  \\s", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CREATEDATE.docx");
```

### Se även

* class [FieldCreateDate](../)
* namnutrymme [Aspose.Words.Fields](../../fieldcreatedate/)
* hopsättning [Aspose.Words](../../../)


