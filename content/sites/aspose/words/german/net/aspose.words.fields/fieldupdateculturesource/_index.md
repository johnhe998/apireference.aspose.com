---
title: Enum FieldUpdateCultureSource
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fields.FieldUpdateCultureSource opsomming. Gibt an welche Kultur während der Feldaktualisierung verwendet werden soll.
type: docs
weight: 2410
url: /de/net/aspose.words.fields/fieldupdateculturesource/
---
## FieldUpdateCultureSource enumeration

Gibt an, welche Kultur während der Feldaktualisierung verwendet werden soll.

```csharp
public enum FieldUpdateCultureSource
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| CurrentThread | `0` | Die Kultur des aktuellen Ausführungsthreads wird zum Aktualisieren von Feldern verwendet. |
| FieldCode | `1` | Die in den Feldformatierungseigenschaften per Spracheinstellung angegebene Kultur wird verwendet. |

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

* namensraum [Aspose.Words.Fields](../../aspose.words.fields/)
* Montage [Aspose.Words](../../)


