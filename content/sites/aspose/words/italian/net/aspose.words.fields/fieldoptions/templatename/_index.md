---
title: FieldOptions.TemplateName
second_title: Aspose.Words per .NET API Reference
description: FieldOptions proprietà. Ottiene o imposta il nome file del modello utilizzato dal documento.
type: docs
weight: 170
url: /it/net/aspose.words.fields/fieldoptions/templatename/
---
## FieldOptions.TemplateName property

Ottiene o imposta il nome file del modello utilizzato dal documento.

```csharp
public string TemplateName { get; set; }
```

### Osservazioni

Questa proprietà è utilizzata dal[`FieldTemplate`](../../fieldtemplate/) campo se il[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) la proprietà è vuota.

Se questa proprietà è vuota, il nome del file modello predefinito`Normal.dotm` viene usato.

### Esempi

Mostra come utilizzare un campo MODELLO per visualizzare la posizione del file system locale del modello di un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Possiamo impostare un nome modello usando i campi. Questa proprietà viene utilizzata quando "doc.AttachedTemplate" è vuoto.
// Se questa proprietà è vuota, viene utilizzato il nome del file modello predefinito "Normal.dotm".
doc.FieldOptions.TemplateName = string.Empty;

FieldTemplate field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
Assert.AreEqual(" TEMPLATE ", field.GetFieldCode());

builder.Writeln();
field = (FieldTemplate)builder.InsertField(FieldType.FieldTemplate, false);
field.IncludeFullPath = true;

Assert.AreEqual(" TEMPLATE  \\p", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TEMPLATE.docx");
```

### Guarda anche

* class [FieldOptions](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldoptions/)
* assemblea [Aspose.Words](../../../)


