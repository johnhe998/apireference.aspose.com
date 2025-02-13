---
title: ToaCategories.DefaultCategories
second_title: Aspose.Words per .NET API Reference
description: ToaCategories proprietà. Ottiene la tabella predefinita delle categorie di autorizzazioni.
type: docs
weight: 20
url: /it/net/aspose.words.fields/toacategories/defaultcategories/
---
## ToaCategories.DefaultCategories property

Ottiene la tabella predefinita delle categorie di autorizzazioni.

```csharp
public static ToaCategories DefaultCategories { get; }
```

### Osservazioni

Usa il[`ToaCategories`](../../fieldoptions/toacategories/) proprietà per specificare la tabella delle categorie di autorità per un singolo documento.

### Esempi

Mostra come specificare un insieme di categorie per i campi TOA.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// I campi TOA possono filtrare le loro voci in base alle categorie definite in questa raccolta.
ToaCategories toaCategories = new ToaCategories();
doc.FieldOptions.ToaCategories = toaCategories;

// Questa raccolta di categorie include valori predefiniti, che possiamo sovrascrivere con valori personalizzati.
Assert.AreEqual("Cases", toaCategories[1]);
Assert.AreEqual("Statutes", toaCategories[2]);

toaCategories[1] = "My Category 1";
toaCategories[2] = "My Category 2";

// Possiamo sempre accedere ai valori predefiniti tramite questa raccolta.
Assert.AreEqual("Cases", ToaCategories.DefaultCategories[1]);
Assert.AreEqual("Statutes", ToaCategories.DefaultCategories[2]);

// Inserisci 2 campi TOA. I campi TOA creano una voce per ogni campo AT nel documento.
// Usa l'opzione "\c" per selezionare l'indice di una categoria dalla nostra collezione.
// Con questa opzione, un campo TOA raccoglierà solo voci dai campi TA che
// hanno anche un'opzione "\c" con un indice di categoria corrispondente. Verrà visualizzato anche ogni campo TOA
// il nome della categoria a cui punta l'opzione "\c".
builder.InsertField("TOA \\c 1 \\h", null);
builder.InsertField("TOA \\c 2 \\h", null);
builder.InsertBreak(BreakType.PageBreak);

// Inserisce voci TOA in 2 categorie. Il nostro primo campo TOA riceverà una voce,
// dal secondo campo TA la cui opzione "\c" punta anche alla prima categoria.
// Il secondo campo TOA conterrà due voci dagli altri due campi TA.
builder.InsertField("TA \\c 2 \\l \"entry 1\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 1 \\l \"entry 2\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 2 \\l \"entry 3\"");

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.TOA.Categories.docx");
```

### Guarda anche

* class [ToaCategories](../)
* spazio dei nomi [Aspose.Words.Fields](../../toacategories/)
* assemblea [Aspose.Words](../../../)


