---
title: DocumentProperty.ToDouble
second_title: Referencia de API de Aspose.Words para .NET
description: DocumentProperty método. Devuelve el valor de la propiedad como double.
type: docs
weight: 90
url: /es/net/aspose.words.properties/documentproperty/todouble/
---
## DocumentProperty.ToDouble method

Devuelve el valor de la propiedad como double.

```csharp
public double ToDouble()
```

### Observaciones

Lanza una excepción si el tipo de propiedad no esNumber .

### Ejemplos

Muestra varios métodos de conversión de tipos de propiedades de documentos personalizados.

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

### Ver también

* class [DocumentProperty](../)
* espacio de nombres [Aspose.Words.Properties](../../documentproperty/)
* asamblea [Aspose.Words](../../../)


