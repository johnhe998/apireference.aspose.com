---
title: Class DocumentPropertyCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Properties.DocumentPropertyCollection classe. Classe base perBuiltInDocumentProperties eCustomDocumentProperties raccolte.
type: docs
weight: 4230
url: /it/net/aspose.words.properties/documentpropertycollection/
---
## DocumentPropertyCollection class

Classe base per[`BuiltInDocumentProperties`](../builtindocumentproperties/) e[`CustomDocumentProperties`](../customdocumentproperties/) raccolte.

```csharp
public abstract class DocumentPropertyCollection : IEnumerable<DocumentProperty>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.properties/documentpropertycollection/count/) { get; } | Ottiene il numero di elementi nella raccolta. |
| [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Restituisce a[`DocumentProperty`](../documentproperty/) oggetto per indice. |
| virtual [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Restituisce a[`DocumentProperty`](../documentproperty/) oggetto dal nome della proprietà. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Clear](../../aspose.words.properties/documentpropertycollection/clear/)() | Rimuove tutte le proprietà dalla raccolta. |
| [Contains](../../aspose.words.properties/documentpropertycollection/contains/)(string) | Restituisce true se nella raccolta esiste una proprietà con il nome specificato. |
| [GetEnumerator](../../aspose.words.properties/documentpropertycollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta. |
| [IndexOf](../../aspose.words.properties/documentpropertycollection/indexof/)(string) | Ottiene l'indice di una proprietà per nome. |
| [Remove](../../aspose.words.properties/documentpropertycollection/remove/)(string) | Rimuove una proprietà con il nome specificato dalla raccolta. |
| [RemoveAt](../../aspose.words.properties/documentpropertycollection/removeat/)(int) | Rimuove una proprietà in corrispondenza dell'indice specificato. |

### Osservazioni

I nomi delle proprietà non fanno distinzione tra maiuscole e minuscole.

Le proprietà nella raccolta sono ordinate alfabeticamente per nome.

### Esempi

Mostra come lavorare con le proprietà personalizzate di un documento.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Le proprietà del documento personalizzate sono coppie chiave-valore che possiamo aggiungere al documento.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// La raccolta ordina le proprietà personalizzate in ordine alfabetico.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Stampa ogni proprietà personalizzata nel documento.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Visualizza il valore di una proprietà personalizzata utilizzando un campo DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Possiamo trovare queste proprietà personalizzate in Microsoft Word tramite "File" -> "Proprietà" > "Proprietà avanzate" > "Costume".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Di seguito sono riportati tre modi per rimuovere le proprietà personalizzate da un documento.
// 1 - Rimuovi per indice:
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Rimuovi per nome:
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Svuota l'intera collezione in una volta:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Guarda anche

* class [BuiltInDocumentProperties](../builtindocumentproperties/)
* class [CustomDocumentProperties](../customdocumentproperties/)
* class [DocumentProperty](../documentproperty/)
* spazio dei nomi [Aspose.Words.Properties](../../aspose.words.properties/)
* assemblea [Aspose.Words](../../)


