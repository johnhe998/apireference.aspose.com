---
title: DocumentProperty.ToString
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentProperty methode. Gibt den Eigenschaftswert als Zeichenfolge zurück die gemäß dem aktuellen Gebietsschema formatiert ist.
type: docs
weight: 110
url: /de/net/aspose.words.properties/documentproperty/tostring/
---
## DocumentProperty.ToString method

Gibt den Eigenschaftswert als Zeichenfolge zurück, die gemäß dem aktuellen Gebietsschema formatiert ist.

```csharp
public override string ToString()
```

### Bemerkungen

Konvertiert eine boolesche Eigenschaft in "Y" oder "N". Konvertiert eine Datumseigenschaft in einen kurzen Datumsstring. Konvertiert für alle anderen Typen eine Eigenschaft mit Object.ToString().

### Beispiele

Zeigt verschiedene Typkonvertierungsmethoden von benutzerdefinierten Dokumenteigenschaften.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

DateTime authDate = DateTime.Today;
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", authDate);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

Assert.AreEqual(true, properties["Authorized"].ToBool());
Assert.AreEqual("John Doe", properties["Authorized By"].ToString());
Assert.AreEqual(authDate, properties["Authorized Date"].ToDateTime());
Assert.AreEqual(1, properties["Authorized Revision"].ToInt());
Assert.AreEqual(123.45d, properties["Authorized Amount"].ToDouble());
```

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

* class [DocumentProperty](../)
* namensraum [Aspose.Words.Properties](../../documentproperty/)
* Montage [Aspose.Words](../../../)


