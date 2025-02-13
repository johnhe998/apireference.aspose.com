---
title: StructuredDocumentTag.CalendarType
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTag fast egendom. Anger typen av kalender för detta SDT . Standard ärDefault
type: docs
weight: 50
url: /sv/net/aspose.words.markup/structureddocumenttag/calendartype/
---
## StructuredDocumentTag.CalendarType property

Anger typen av kalender för detta **SDT** . Standard ärDefault

```csharp
public SdtCalendarType CalendarType { get; set; }
```

### Anmärkningar

Åtkomst till den här egenskapen fungerar bara förDate SDT-typ.

För alla andra SDT-typer kommer undantag att förekomma.

### Exempel

Visar hur man uppmanar användaren att ange ett datum med en strukturerad dokumenttagg.

```csharp
Document doc = new Document();

// Infoga en strukturerad dokumenttagg som uppmanar användaren att ange ett datum.
// I Microsoft Word är detta element känt som en "Date picker content control".
// När vi klickar på pilen till höger på den här taggen i Microsoft Word,
// vi kommer att se en popup i form av en klickbar kalender.
// Vi kan använda den popupen för att välja ett datum som taggen ska visa.
StructuredDocumentTag sdtDate = new StructuredDocumentTag(doc, SdtType.Date, MarkupLevel.Inline);

// Visa datumet enligt språket i Saudiarabien.
sdtDate.DateDisplayLocale = CultureInfo.GetCultureInfo("ar-SA").LCID;

// Ställ in formatet för att visa datumet.
sdtDate.DateDisplayFormat = "dd MMMM, yyyy";
sdtDate.DateStorageFormat = SdtDateStorageFormat.DateTime;

// Visa datum enligt Hijri-kalendern.
sdtDate.CalendarType = SdtCalendarType.Hijri;

// Innan användaren väljer ett datum i Microsoft Word kommer taggen att visa texten "Klicka här för att ange ett datum.".
// Enligt taggens kalender, ställ in egenskapen "FullDate" för att få taggen att visa ett standarddatum.
sdtDate.FullDate = new DateTime(1440, 10, 20);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(sdtDate);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Date.docx");
```

### Se även

* enum [SdtCalendarType](../../sdtcalendartype/)
* class [StructuredDocumentTag](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttag/)
* hopsättning [Aspose.Words](../../../)


