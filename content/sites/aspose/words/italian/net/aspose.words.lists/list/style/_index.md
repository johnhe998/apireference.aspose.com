---
title: List.Style
second_title: Aspose.Words per .NET API Reference
description: List proprietà. Ottiene lo stile di elenco a cui fa riferimento o definisce questo elenco.
type: docs
weight: 80
url: /it/net/aspose.words.lists/list/style/
---
## List.Style property

Ottiene lo stile di elenco a cui fa riferimento o definisce questo elenco.

```csharp
public Style Style { get; }
```

### Osservazioni

Se questo elenco non è associato a uno stile di elenco, la proprietà restituirà null.

Un elenco potrebbe essere un riferimento a uno stile di elenco, in questo caso[`IsListStyleReference`](../isliststylereference/) sarà vero.

Un elenco potrebbe essere una definizione di uno stile di elenco, in questo caso[`IsListStyleDefinition`](../isliststyledefinition/) sarà vero. Tale elenco non può essere applicato direttamente ai paragrafi del documento.

### Esempi

Mostra come creare uno stile elenco e utilizzarlo in un documento.

```csharp
Document doc = new Document();

// Un elenco ci consente di organizzare e decorare insiemi di paragrafi con simboli e rientri prefissi.
// Possiamo creare liste nidificate aumentando il livello di rientro. 
// Possiamo iniziare e terminare un elenco utilizzando la proprietà "ListFormat" di un generatore di documenti. 
// Ogni paragrafo che aggiungiamo tra l'inizio e la fine di un elenco diventerà un elemento nell'elenco.
// Possiamo contenere un intero oggetto List all'interno di uno stile.
Style listStyle = doc.Styles.Add(StyleType.List, "MyListStyle");

List list1 = listStyle.List;

Assert.True(list1.IsListStyleDefinition);
Assert.False(list1.IsListStyleReference);
Assert.True(list1.IsMultiLevel);
Assert.AreEqual(listStyle, list1.Style);

// Modifica l'aspetto di tutti i livelli di elenco nel nostro elenco.
foreach (ListLevel level in list1.ListLevels)
{
    level.Font.Name = "Verdana";
    level.Font.Color = Color.Blue;
    level.Font.Bold = true;
}

DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Using list style first time:");

// Crea un altro elenco da un elenco all'interno di uno stile.
List list2 = doc.Lists.Add(listStyle);

Assert.False(list2.IsListStyleDefinition);
Assert.True(list2.IsListStyleReference);
Assert.AreEqual(listStyle, list2.Style);

// Aggiungi alcuni elementi dell'elenco che il nostro elenco formatterà.
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Writeln("Using list style second time:");

// Crea e applica un altro elenco in base allo stile dell'elenco.
List list3 = doc.Lists.Add(listStyle);
builder.ListFormat.List = list3;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateAndUseListStyle.docx");
```

### Guarda anche

* class [Style](../../../aspose.words/style/)
* class [List](../)
* spazio dei nomi [Aspose.Words.Lists](../../list/)
* assemblea [Aspose.Words](../../../)


