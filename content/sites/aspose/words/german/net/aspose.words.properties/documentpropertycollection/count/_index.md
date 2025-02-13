---
title: DocumentPropertyCollection.Count
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentPropertyCollection eigendom. Ruft die Anzahl der Elemente in der Sammlung ab.
type: docs
weight: 10
url: /de/net/aspose.words.properties/documentpropertycollection/count/
---
## DocumentPropertyCollection.Count property

Ruft die Anzahl der Elemente in der Sammlung ab.

```csharp
public int Count { get; }
```

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

* class [DocumentPropertyCollection](../)
* namensraum [Aspose.Words.Properties](../../documentpropertycollection/)
* Montage [Aspose.Words](../../../)


