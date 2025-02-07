---
title: FieldDocVariable.VariableName
second_title: Aspose.Words per .NET API Reference
description: FieldDocVariable proprietà. Ottiene o imposta il nome della variabile del documento da recuperare.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

Ottiene o imposta il nome della variabile del documento da recuperare.

```csharp
public string VariableName { get; set; }
```

### Esempi

Mostra come utilizzare i campi DOCPROPERTY per visualizzare le proprietà e le variabili del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Di seguito sono riportati due modi per utilizzare i campi DOCPROPERTY.
// 1 - Visualizza una proprietà incorporata:
// Imposta un valore personalizzato per la proprietà incorporata "Categoria", quindi inserisci un campo DOCPROPERTY che vi faccia riferimento.
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - Visualizza una variabile del documento personalizzata:
// Definisci una variabile personalizzata, quindi fai riferimento a tale variabile con un campo DOCPROPERTY.
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### Guarda anche

* class [FieldDocVariable](../)
* spazio dei nomi [Aspose.Words.Fields](../../fielddocvariable/)
* assemblea [Aspose.Words](../../../)


