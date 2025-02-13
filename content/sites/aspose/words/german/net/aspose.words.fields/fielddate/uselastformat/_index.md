---
title: FieldDate.UseLastFormat
second_title: Aspose.Words für .NET-API-Referenz
description: FieldDate eigendom. Ruft ab oder legt fest ob beim Einfügen eines neuen DATEFelds ein zuletzt von der Hostanwendung verwendetes Format verwendet werden soll.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fielddate/uselastformat/
---
## FieldDate.UseLastFormat property

Ruft ab oder legt fest, ob beim Einfügen eines neuen DATE-Felds ein zuletzt von der Hostanwendung verwendetes Format verwendet werden soll.

```csharp
public bool UseLastFormat { get; set; }
```

### Beispiele

Zeigt, wie DATE-Felder verwendet werden, um Datumsangaben gemäß verschiedener Arten von Kalendern anzuzeigen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wenn wir möchten, dass der Text im Dokument immer das richtige Datum anzeigt, können wir ein DATE-Feld verwenden.
// Nachfolgend sind drei Arten von Kulturkalendern aufgeführt, die ein DATE-Feld verwenden kann, um ein Datum anzuzeigen.
// 1 - Islamischer Mondkalender:
FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLunarCalendar = true;
Assert.AreEqual(" DATE  \\h", field.GetFieldCode());
builder.Writeln();

// 2 - Umm al-Qura Kalender:
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseUmAlQuraCalendar = true;
Assert.AreEqual(" DATE  \\u", field.GetFieldCode());
builder.Writeln();

// 3 - Indischer Nationalkalender:
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseSakaEraCalendar = true;
Assert.AreEqual(" DATE  \\s", field.GetFieldCode());
builder.Writeln();

// Fügen Sie ein DATE-Feld ein und setzen Sie seinen Kalendertyp auf den zuletzt von der Hostanwendung verwendeten.
// In Microsoft Word ist der Typ der zuletzt verwendete in der Insert -> Text -> Dialogfeld Datum und Uhrzeit.
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLastFormat = true;
Assert.AreEqual(" DATE  \\l", field.GetFieldCode());
builder.Writeln();

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATE.docx");
```

### Siehe auch

* class [FieldDate](../)
* namensraum [Aspose.Words.Fields](../../fielddate/)
* Montage [Aspose.Words](../../../)


