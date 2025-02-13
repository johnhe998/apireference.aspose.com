---
title: Field.Result
second_title: Aspose.Words für .NET-API-Referenz
description: Field eigendom. Liest oder setzt Text der zwischen dem Feldtrennzeichen und dem Feldende steht.
type: docs
weight: 70
url: /de/net/aspose.words.fields/field/result/
---
## Field.Result property

Liest oder setzt Text, der zwischen dem Feldtrennzeichen und dem Feldende steht.

```csharp
public string Result { get; set; }
```

### Beispiele

Zeigt, wie ein Feld mithilfe eines Feldcodes in ein Dokument eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Diese Überladung der InsertField-Methode aktualisiert automatisch eingefügte Felder.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### Siehe auch

* class [Field](../)
* namensraum [Aspose.Words.Fields](../../field/)
* Montage [Aspose.Words](../../../)


