---
title: FieldOptions.FieldUpdateCultureSource
second_title: Aspose.Words für .NET-API-Referenz
description: FieldOptions eigendom. Gibt an welche Kultur verwendet werden soll um das Feldergebnis zu formatieren.
type: docs
weight: 100
url: /de/net/aspose.words.fields/fieldoptions/fieldupdateculturesource/
---
## FieldOptions.FieldUpdateCultureSource property

Gibt an, welche Kultur verwendet werden soll, um das Feldergebnis zu formatieren.

```csharp
public FieldUpdateCultureSource FieldUpdateCultureSource { get; set; }
```

### Bemerkungen

Standardmäßig wird die Kultur des aktuellen Threads verwendet.

Die Einstellung wirkt sich nur auf Datums-/Uhrzeitfelder mit Formatumschaltung \\@ aus.

### Beispiele

Zeigt, wie die Quelle der Kultur angegeben wird, die für die Datumsformatierung während einer Feldaktualisierung oder eines Seriendrucks verwendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Zwei Briefvorlagenfelder mit deutschem Gebietsschema einfügen.
builder.Font.LocaleId = new CultureInfo("de-DE").LCID;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

// Setzt die aktuelle Kultur auf US-Englisch, nachdem der ursprüngliche Wert in einer Variablen beibehalten wurde.
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");

// Diese Zusammenführung verwendet die Kultur des aktuellen Threads, um das Datum zu formatieren, US-Englisch.
doc.MailMerge.Execute(new[] { "Date1" }, new object[] { new DateTime(2020, 1, 01) });

// Konfigurieren Sie die nächste Zusammenführung, um ihren Kulturwert aus dem Feldcode zu beziehen. Der Wert dieser Kultur wird deutsch sein.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.MailMerge.Execute(new[] { "Date2" }, new object[] { new DateTime(2020, 1, 01) });

// Das erste Merge-Ergebnis enthält ein englisch formatiertes Datum, das zweite ein deutsch formatiertes Datum.
Assert.AreEqual("Wednesday, 1 January 2020 - Mittwoch, 1 Januar 2020", doc.Range.Text.Trim());

// Stellen Sie die ursprüngliche Kultur des Threads wieder her.
Thread.CurrentThread.CurrentCulture = currentCulture;
```

### Siehe auch

* enum [FieldUpdateCultureSource](../../fieldupdateculturesource/)
* class [FieldOptions](../)
* namensraum [Aspose.Words.Fields](../../fieldoptions/)
* Montage [Aspose.Words](../../../)


