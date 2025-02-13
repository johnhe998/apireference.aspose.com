---
title: Class DropDownItemCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fields.DropDownItemCollection classe. Una raccolta di stringhe che rappresentano tutti gli elementi in un campo modulo a discesa.
type: docs
weight: 1350
url: /it/net/aspose.words.fields/dropdownitemcollection/
---
## DropDownItemCollection class

Una raccolta di stringhe che rappresentano tutti gli elementi in un campo modulo a discesa.

```csharp
public class DropDownItemCollection : IEnumerable<string>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.fields/dropdownitemcollection/count/) { get; } | Ottiene il numero di elementi contenuti nella raccolta. |
| [Item](../../aspose.words.fields/dropdownitemcollection/item/) { get; set; } | Ottiene o imposta l'elemento in corrispondenza dell'indice specificato. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words.fields/dropdownitemcollection/add/)(string) | Aggiunge una stringa alla fine della raccolta. |
| [Clear](../../aspose.words.fields/dropdownitemcollection/clear/)() | Rimuove tutti gli elementi dalla raccolta. |
| [Contains](../../aspose.words.fields/dropdownitemcollection/contains/)(string) | Determina se la raccolta contiene il valore specificato. |
| [GetEnumerator](../../aspose.words.fields/dropdownitemcollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta. |
| [IndexOf](../../aspose.words.fields/dropdownitemcollection/indexof/)(string) | Restituisce l'indice in base zero del valore specificato nella raccolta. |
| [Insert](../../aspose.words.fields/dropdownitemcollection/insert/)(int, string) | Inserisce una stringa nella raccolta in corrispondenza dell'indice specificato. |
| [Remove](../../aspose.words.fields/dropdownitemcollection/remove/)(string) | Rimuove il valore specificato dalla raccolta. |
| [RemoveAt](../../aspose.words.fields/dropdownitemcollection/removeat/)(int) | Rimuove un valore in corrispondenza dell'indice specificato. |

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

* class [FormField](../formfield/)
* property [DropDownItems](../formfield/dropdownitems/)
* spazio dei nomi [Aspose.Words.Fields](../../aspose.words.fields/)
* assemblea [Aspose.Words](../../)


