---
title: DocumentBuilder.MoveToField
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Sposta il cursore su un campo del documento.
type: docs
weight: 510
url: /it/net/aspose.words/documentbuilder/movetofield/
---
## DocumentBuilder.MoveToField method

Sposta il cursore su un campo del documento.

```csharp
public void MoveToField(Field field, bool isAfter)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| field | Field | Il campo in cui spostare il cursore. |
| isAfter | Boolean | Se true, sposta il cursore in modo che si trovi dopo la fine del campo. Se false, sposta il cursore in modo che sia prima dell'inizio del campo. |

### Esempi

Mostra come spostare il cursore del punto di inserimento del nodo di un generatore di documenti in un campo specifico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un campo usando DocumentBuilder e aggiungi una sequenza di testo dopo di esso.
Field field = builder.InsertField(" AUTHOR \"John Doe\" ");

// Il cursore del builder è attualmente alla fine del documento.
Assert.Null(builder.CurrentNode);

// Sposta il cursore sul campo mentre specifichi se posizionare quel cursore prima o dopo il campo.
builder.MoveToField(field, moveCursorToAfterTheField);

// Nota che il cursore è fuori dal campo in entrambi i casi.
// Ciò significa che non possiamo modificare il campo utilizzando il builder in questo modo.
// Per modificare un campo, possiamo utilizzare il metodo MoveTo del builder su FieldStart di un campo
// o nodo FieldSeparator per posizionare il cursore all'interno.
if (moveCursorToAfterTheField)
{
    Assert.Null(builder.CurrentNode);
    builder.Write(" Text immediately after the field.");

    Assert.AreEqual("\u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015 Text immediately after the field.", 
        doc.GetText().Trim());
}
else
{
    Assert.AreEqual(field.Start, builder.CurrentNode);
    builder.Write("Text immediately before the field. ");

    Assert.AreEqual("Text immediately before the field. \u0013 AUTHOR \"John Doe\" \u0014John Doe\u0015", 
        doc.GetText().Trim());
}
```

### Guarda anche

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


