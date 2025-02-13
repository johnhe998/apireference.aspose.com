---
title: StructuredDocumentTag.DateDisplayFormat
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTag fast egendom. Sträng som representerar formatet som datum visas i. Kan inte vara null. Datumen för engelska USA är mm/dd/åååå
type: docs
weight: 90
url: /sv/net/aspose.words.markup/structureddocumenttag/datedisplayformat/
---
## StructuredDocumentTag.DateDisplayFormat property

Sträng som representerar formatet som datum visas i. Kan inte vara null. Datumen för engelska (USA) är "mm/dd/åååå"

```csharp
public string DateDisplayFormat { get; set; }
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

* class [StructuredDocumentTag](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttag/)
* hopsättning [Aspose.Words](../../../)


