---
title: DocumentProperty.ToBool
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentProperty methode. Gibt den Eigenschaftswert als bool zurück.
type: docs
weight: 60
url: /de/net/aspose.words.properties/documentproperty/tobool/
---
## DocumentProperty.ToBool method

Gibt den Eigenschaftswert als bool zurück.

```csharp
public bool ToBool()
```

### Bemerkungen

Löst eine Ausnahme aus, wenn der Eigenschaftstyp nicht istBoolean.

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

### Siehe auch

* class [DocumentProperty](../)
* namensraum [Aspose.Words.Properties](../../documentproperty/)
* Montage [Aspose.Words](../../../)


