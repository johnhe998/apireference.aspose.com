---
title: DocumentPropertyCollection.Item
second_title: Aspose.Words per .NET API Reference
description: DocumentPropertyCollection proprietà. Restituisce aDocumentProperty oggetto dal nome della proprietà.
type: docs
weight: 20
url: /it/net/aspose.words.properties/documentpropertycollection/item/
---
## DocumentPropertyCollection indexer (1 of 2)

Restituisce a[`DocumentProperty`](../../documentproperty/) oggetto dal nome della proprietà.

```csharp
public virtual DocumentProperty this[string name] { get; }
```

| Parametro | Descrizione |
| --- | --- |
| name | Il nome senza distinzione tra maiuscole e minuscole della proprietà da recuperare. |

### Osservazioni

Restituisce null se non viene trovata una proprietà con il nome specificato.

### Esempi

Mostra come creare una proprietà del documento personalizzata che contiene una data e un'ora.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("AuthorizationDate", DateTime.Now);

Console.WriteLine($"Document authorized on {doc.CustomDocumentProperties["AuthorizationDate"].ToDateTime()}");
```

### Guarda anche

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* spazio dei nomi [Aspose.Words.Properties](../../documentpropertycollection/)
* assemblea [Aspose.Words](../../../)

---

## DocumentPropertyCollection indexer (2 of 2)

Restituisce a[`DocumentProperty`](../../documentproperty/) oggetto per indice.

```csharp
public DocumentProperty this[int index] { get; }
```

| Parametro | Descrizione |
| --- | --- |
| index | Indice a base zero del[`DocumentProperty`](../../documentproperty/) recuperare. |

### Esempi

Mostra come lavorare con le proprietà del documento personalizzate.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Ogni documento contiene una raccolta di proprietà personalizzate che, come le proprietà integrate, sono coppie chiave-valore.
// Il documento ha un elenco fisso di proprietà integrate. L'utente crea tutte le proprietà personalizzate. 
Assert.AreEqual("Value of custom document property", doc.CustomDocumentProperties["CustomProperty"].ToString());

doc.CustomDocumentProperties.Add("CustomProperty2", "Value of custom document property #2");

Console.WriteLine("Custom Properties:");
foreach (var customDocumentProperty in doc.CustomDocumentProperties)
{
    Console.WriteLine(customDocumentProperty.Name);
    Console.WriteLine($"\tType:\t{customDocumentProperty.Type}");
    Console.WriteLine($"\tValue:\t\"{customDocumentProperty.Value}\"");
}
```

### Guarda anche

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* spazio dei nomi [Aspose.Words.Properties](../../documentpropertycollection/)
* assemblea [Aspose.Words](../../../)


