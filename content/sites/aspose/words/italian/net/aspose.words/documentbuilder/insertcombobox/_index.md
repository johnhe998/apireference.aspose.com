---
title: DocumentBuilder.InsertComboBox
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Inserisce un campo modulo casella combinata nella posizione corrente.
type: docs
weight: 280
url: /it/net/aspose.words/documentbuilder/insertcombobox/
---
## DocumentBuilder.InsertComboBox method

Inserisce un campo modulo casella combinata nella posizione corrente.

```csharp
public FormField InsertComboBox(string name, string[] items, int selectedIndex)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| name | String | Il nome del campo del modulo. Può essere una stringa vuota. Il valore più lungo di 20 caratteri verrà troncato. |
| items | String[] | Gli elementi del ComboBox. Il massimo è di 25 elementi. |
| selectedIndex | Int32 | L'indice dell'elemento selezionato nel ComboBox. |

### Valore di ritorno

Il nodo del campo modulo appena inserito.

### Osservazioni

Se specifichi un nome per il campo modulo, viene creato automaticamente un segnalibro con lo stesso nome.

### Esempi

Mostra come inserire un campo modulo casella combinata in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce un modulo che richiede all'utente di selezionare una delle voci dal menu.
builder.Write("Pick a fruit: ");
string[] items = { "Apple", "Banana", "Cherry" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertComboBox.docx");
```

Mostra come creare campi modulo.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// I campi modulo sono oggetti nel documento con cui l'utente può interagire quando viene richiesto di immettere valori.
// Possiamo crearli utilizzando un generatore di documenti e di seguito sono riportati due modi per farlo.
// 1 - Input di testo di base:
builder.InsertTextInput("My text input", TextFormFieldType.Regular, 
    "", "Enter your name here", 30);

// 2 - Casella combinata con testo di richiesta e un intervallo di valori possibili:
string[] items =
{
    "-- Select your favorite footwear --", "Sneakers", "Oxfords", "Flip-flops", "Other"
};

builder.InsertParagraph();
builder.InsertComboBox("My combo box", items, 0);

builder.Document.Save(ArtifactsDir + "DocumentBuilder.CreateForm.docx");
```

### Guarda anche

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


