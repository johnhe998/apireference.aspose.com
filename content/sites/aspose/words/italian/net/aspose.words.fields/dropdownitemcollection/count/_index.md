---
title: DropDownItemCollection.Count
second_title: Aspose.Words per .NET API Reference
description: DropDownItemCollection proprietà. Ottiene il numero di elementi contenuti nella raccolta.
type: docs
weight: 10
url: /it/net/aspose.words.fields/dropdownitemcollection/count/
---
## DropDownItemCollection.Count property

Ottiene il numero di elementi contenuti nella raccolta.

```csharp
public int Count { get; }
```

### Esempi

Mostra come inserire un campo casella combinata e modificare gli elementi nella sua raccolta di elementi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci una casella combinata, quindi verifica la sua raccolta di elementi a discesa.
// In Microsoft Word, l'utente farà clic sulla casella combinata,
// e quindi scegli uno degli elementi di testo nella raccolta da visualizzare.
string[] items = { "One", "Two", "Three" };
FormField comboBoxField = builder.InsertComboBox("DropDown", items, 0);
DropDownItemCollection dropDownItems = comboBoxField.DropDownItems;

Assert.AreEqual(3, dropDownItems.Count);
Assert.AreEqual("One", dropDownItems[0]);
Assert.AreEqual(1, dropDownItems.IndexOf("Two"));
Assert.IsTrue(dropDownItems.Contains("Three"));

// Esistono due modi per aggiungere un nuovo elemento a una raccolta esistente di elementi della casella a discesa.
// 1 - Aggiungi un elemento alla fine della raccolta:
dropDownItems.Add("Four");

// 2 - Inserisci un elemento prima di un altro elemento in un indice specificato:
dropDownItems.Insert(3, "Three and a half");

Assert.AreEqual(5, dropDownItems.Count);

// Scorri la raccolta e stampa ogni elemento.
using (IEnumerator<string> dropDownCollectionEnumerator = dropDownItems.GetEnumerator())
    while (dropDownCollectionEnumerator.MoveNext())
        Console.WriteLine(dropDownCollectionEnumerator.Current);

// Esistono due modi per rimuovere elementi da una raccolta di elementi a discesa.
// 1 - Rimuove un elemento con contenuto uguale alla stringa passata:
dropDownItems.Remove("Four");

// 2 - Rimuovere un elemento in un indice:
dropDownItems.RemoveAt(3);

Assert.AreEqual(3, dropDownItems.Count);
Assert.IsFalse(dropDownItems.Contains("Three and a half"));
Assert.IsFalse(dropDownItems.Contains("Four"));

doc.Save(ArtifactsDir + "FormFields.DropDownItemCollection.html");

// Svuota l'intera raccolta di elementi a discesa.
dropDownItems.Clear();
```

### Guarda anche

* class [DropDownItemCollection](../)
* spazio dei nomi [Aspose.Words.Fields](../../dropdownitemcollection/)
* assemblea [Aspose.Words](../../../)


