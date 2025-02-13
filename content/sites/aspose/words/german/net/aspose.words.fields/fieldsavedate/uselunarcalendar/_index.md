---
title: FieldSaveDate.UseLunarCalendar
second_title: Aspose.Words für .NET-API-Referenz
description: FieldSaveDate eigendom. Ruft ab oder legt fest ob der HijriMondkalender oder der hebräische Mondkalender verwendet werden soll.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldsavedate/uselunarcalendar/
---
## FieldSaveDate.UseLunarCalendar property

Ruft ab oder legt fest, ob der Hijri-Mondkalender oder der hebräische Mondkalender verwendet werden soll.

```csharp
public bool UseLunarCalendar { get; set; }
```

### Beispiele

Zeigt, wie das Feld SAVEDATE verwendet wird, um das Datum/die Uhrzeit des letzten Speichervorgangs des Dokuments anzuzeigen, der mit Microsoft Word durchgeführt wurde.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln(" Date this document was last saved:");

// Wir können das Feld SAVEDATE verwenden, um das Datum und die Uhrzeit des letzten Speichervorgangs im Dokument anzuzeigen.
// Der Speichervorgang, auf den sich diese Felder beziehen, ist das manuelle Speichern in einer Anwendung wie Microsoft Word,
// nicht die Save-Methode des Dokuments.
// Nachfolgend sind drei verschiedene Kalendertypen aufgeführt, nach denen das SAVEDATE-Feld das Datum/die Uhrzeit anzeigen kann.
// 1 - Islamischer Mondkalender:
builder.Write("According to the Lunar Calendar - ");
FieldSaveDate field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseLunarCalendar = true;

Assert.AreEqual(" SAVEDATE  \\h", field.GetFieldCode());

// 2 - Umm al-Qura Kalender:
builder.Write("\nAccording to the Umm al-Qura calendar - ");
field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseUmAlQuraCalendar = true;

Assert.AreEqual(" SAVEDATE  \\u", field.GetFieldCode());

// 3 - Indischer Nationalkalender:
builder.Write("\nAccording to the Indian National calendar - ");
field = (FieldSaveDate)builder.InsertField(FieldType.FieldSaveDate, true);
field.UseSakaEraCalendar = true;

Assert.AreEqual(" SAVEDATE  \\s", field.GetFieldCode());

// Die SAVEDATE-Felder beziehen ihre Datums-/Uhrzeitwerte aus der integrierten LastSavedTime-Eigenschaft.
// Die Save-Methode des Dokuments aktualisiert diesen Wert nicht, aber wir können ihn trotzdem manuell aktualisieren.
doc.BuiltInDocumentProperties.LastSavedTime = DateTime.Now;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SAVEDATE.docx");
```

### Siehe auch

* class [FieldSaveDate](../)
* namensraum [Aspose.Words.Fields](../../fieldsavedate/)
* Montage [Aspose.Words](../../../)


