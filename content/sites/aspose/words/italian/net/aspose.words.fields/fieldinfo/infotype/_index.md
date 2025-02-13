---
title: FieldInfo.InfoType
second_title: Aspose.Words per .NET API Reference
description: FieldInfo proprietà. Ottiene o imposta il tipo di proprietà del documento da inserire.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldinfo/infotype/
---
## FieldInfo.InfoType property

Ottiene o imposta il tipo di proprietà del documento da inserire.

```csharp
public string InfoType { get; set; }
```

### Esempi

Mostra come lavorare con i campi INFO.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Imposta un valore per la proprietà incorporata "Commenti", quindi inserisci un campo INFO per visualizzare il valore di quella proprietà.
doc.BuiltInDocumentProperties.Comments = "My comment";
FieldInfo field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.Update();

Assert.AreEqual(" INFO  Comments", field.GetFieldCode());
Assert.AreEqual("My comment", field.Result);

builder.Writeln();

// Impostazione di un valore per la proprietà NewValue del campo e aggiornamento
// il campo sovrascriverà anche la proprietà incorporata corrispondente con il nuovo valore.
field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.NewValue = "New comment";
field.Update();

Assert.AreEqual(" INFO  Comments \"New comment\"", field.GetFieldCode());
Assert.AreEqual("New comment", field.Result);
Assert.AreEqual("New comment", doc.BuiltInDocumentProperties.Comments);

doc.Save(ArtifactsDir + "Field.INFO.docx");
```

### Guarda anche

* class [FieldInfo](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldinfo/)
* assemblea [Aspose.Words](../../../)


