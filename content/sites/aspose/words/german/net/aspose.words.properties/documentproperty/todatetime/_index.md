---
title: DocumentProperty.ToDateTime
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentProperty methode. Gibt den Eigenschaftswert als DateTime in UTC zurück.
type: docs
weight: 80
url: /de/net/aspose.words.properties/documentproperty/todatetime/
---
## DocumentProperty.ToDateTime method

Gibt den Eigenschaftswert als DateTime in UTC zurück.

```csharp
public DateTime ToDateTime()
```

### Bemerkungen

Löst eine Ausnahme aus, wenn der Eigenschaftstyp nicht istDateTime.

Microsoft Word speichert nur den Datumsteil (keine Uhrzeit) für benutzerdefinierte Datumseigenschaften.

### Beispiele

Zeigt, wie eine benutzerdefinierte Dokumenteigenschaft erstellt wird, die ein Datum und eine Uhrzeit enthält.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("AuthorizationDate", DateTime.Now);

Console.WriteLine($"Document authorized on {doc.CustomDocumentProperties["AuthorizationDate"].ToDateTime()}");
```

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

### Siehe auch

* class [DocumentProperty](../)
* namensraum [Aspose.Words.Properties](../../documentproperty/)
* Montage [Aspose.Words](../../../)


