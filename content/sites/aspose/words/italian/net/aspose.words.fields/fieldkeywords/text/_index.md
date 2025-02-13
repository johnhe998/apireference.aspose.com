---
title: FieldKeywords.Text
second_title: Aspose.Words per .NET API Reference
description: FieldKeywords proprietà. Ottiene o imposta il testo delle parole chiave.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldkeywords/text/
---
## FieldKeywords.Text property

Ottiene o imposta il testo delle parole chiave.

```csharp
public string Text { get; set; }
```

### Esempi

Mostra per inserire un campo KEYWORDS.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aggiunge alcune parole chiave, dette anche "tag" in Esplora file.
doc.BuiltInDocumentProperties.Keywords = "Keyword1, Keyword2";

// Il campo KEYWORDS visualizza il valore di questa proprietà.
FieldKeywords field = (FieldKeywords)builder.InsertField(FieldType.FieldKeyword, true);
field.Update();

Assert.AreEqual(" KEYWORDS ", field.GetFieldCode());
Assert.AreEqual("Keyword1, Keyword2", field.Result);

// Impostando un valore per la proprietà Text del campo,
// e quindi l'aggiornamento del campo sovrascriverà anche la proprietà incorporata corrispondente con il nuovo valore.
field.Text = "OverridingKeyword";
field.Update();

Assert.AreEqual(" KEYWORDS  OverridingKeyword", field.GetFieldCode());
Assert.AreEqual("OverridingKeyword", field.Result);
Assert.AreEqual("OverridingKeyword", doc.BuiltInDocumentProperties.Keywords);

doc.Save(ArtifactsDir + "Field.KEYWORDS.docx");
```

### Guarda anche

* class [FieldKeywords](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldkeywords/)
* assemblea [Aspose.Words](../../../)


