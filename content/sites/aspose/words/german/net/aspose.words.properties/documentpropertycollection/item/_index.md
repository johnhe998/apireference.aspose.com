---
title: DocumentPropertyCollection.Item
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentPropertyCollection eigendom. Gibt a zurückDocumentProperty Objekt nach dem Namen der Eigenschaft.
type: docs
weight: 20
url: /de/net/aspose.words.properties/documentpropertycollection/item/
---
## DocumentPropertyCollection indexer (1 of 2)

Gibt a zurück[`DocumentProperty`](../../documentproperty/) Objekt nach dem Namen der Eigenschaft.

```csharp
public virtual DocumentProperty this[string name] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| name | Der Name der abzurufenden Eigenschaft ohne Berücksichtigung der Groß-/Kleinschreibung. |

### Bemerkungen

Gibt null zurück, wenn eine Eigenschaft mit dem angegebenen Namen nicht gefunden wird.

### Beispiele

Zeigt, wie eine benutzerdefinierte Dokumenteigenschaft erstellt wird, die ein Datum und eine Uhrzeit enthält.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("AuthorizationDate", DateTime.Now);

Console.WriteLine($"Document authorized on {doc.CustomDocumentProperties["AuthorizationDate"].ToDateTime()}");
```

### Siehe auch

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* namensraum [Aspose.Words.Properties](../../documentpropertycollection/)
* Montage [Aspose.Words](../../../)

---

## DocumentPropertyCollection indexer (2 of 2)

Gibt a zurück[`DocumentProperty`](../../documentproperty/) Objekt nach Index.

```csharp
public DocumentProperty this[int index] { get; }
```

| Parameter | Beschreibung |
| --- | --- |
| index | Nullbasierter Index der[`DocumentProperty`](../../documentproperty/) abzurufen. |

### Beispiele

Zeigt, wie Sie mit benutzerdefinierten Dokumenteigenschaften arbeiten.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Jedes Dokument enthält eine Sammlung benutzerdefinierter Eigenschaften, die wie die integrierten Eigenschaften Schlüssel-Wert-Paare sind.
// Das Dokument hat eine feste Liste eingebauter Eigenschaften. Der Benutzer erstellt alle benutzerdefinierten Eigenschaften. 
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

### Siehe auch

* class [DocumentProperty](../../documentproperty/)
* class [DocumentPropertyCollection](../)
* namensraum [Aspose.Words.Properties](../../documentpropertycollection/)
* Montage [Aspose.Words](../../../)


