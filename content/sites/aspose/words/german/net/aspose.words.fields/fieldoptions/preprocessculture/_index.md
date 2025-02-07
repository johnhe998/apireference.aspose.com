---
title: FieldOptions.PreProcessCulture
second_title: Aspose.Words für .NET-API-Referenz
description: FieldOptions eigendom. Ruft die Kultur ab oder legt sie fest um Feldwerte vorzuverarbeiten.
type: docs
weight: 150
url: /de/net/aspose.words.fields/fieldoptions/preprocessculture/
---
## FieldOptions.PreProcessCulture property

Ruft die Kultur ab oder legt sie fest, um Feldwerte vorzuverarbeiten.

```csharp
public CultureInfo PreProcessCulture { get; set; }
```

### Bemerkungen

Derzeit wirkt sich diese Eigenschaft nur auf den Wert von aus[`FieldDocProperty`](../../fielddocproperty/) aufstellen.

Der Standardwert ist **Null** . Wenn diese Eigenschaft auf eingestellt ist **Null** , das[`FieldDocProperty`](../../fielddocproperty/) Der Wert des Felds ist preprocessed , wobei die Kultur von der gesteuert wird[`FieldUpdateCultureSource`](../fieldupdateculturesource/) Eigentum.

### Beispiele

Zeigt, wie die Vorverarbeitungskultur festgelegt wird.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Legen Sie die Kultur fest, nach der einige Felder ihre angezeigten Werte formatieren.
doc.FieldOptions.PreProcessCulture = new CultureInfo("de-DE");

Field field = builder.InsertField(" DOCPROPERTY CreateTime");

// Das DOCPROPERTY-Feld zeigt sein Ergebnis formatiert gemäß der Vorverarbeitungskultur an
// Wir haben auf Deutsch eingestellt. Das Feld zeigt das Datum/die Uhrzeit im Format "dd.mm.yyyy hh:mm" an.
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[.]\d{2}[.]\d{4} \d{2}[:]\d{2}").Success);

doc.FieldOptions.PreProcessCulture = CultureInfo.InvariantCulture;
field.Update();

// Nach dem Wechsel zur invarianten Kultur verwendet das Feld DOCPROPERTY das Format "mm/dd/yyyy hh:mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[/]\d{2}[/]\d{4} \d{2}[:]\d{2}").Success);
```

### Siehe auch

* class [FieldOptions](../)
* namensraum [Aspose.Words.Fields](../../fieldoptions/)
* Montage [Aspose.Words](../../../)


