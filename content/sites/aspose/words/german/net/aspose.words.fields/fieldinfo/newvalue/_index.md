---
title: FieldInfo.NewValue
second_title: Aspose.Words für .NET-API-Referenz
description: FieldInfo eigendom. Ruft einen optionalen Wert ab der die Eigenschaft aktualisiert oder legt ihn fest.
type: docs
weight: 30
url: /de/net/aspose.words.fields/fieldinfo/newvalue/
---
## FieldInfo.NewValue property

Ruft einen optionalen Wert ab, der die Eigenschaft aktualisiert, oder legt ihn fest.

```csharp
public string NewValue { get; set; }
```

### Beispiele

Zeigt, wie mit INFO-Feldern gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Legen Sie einen Wert für die eingebaute Eigenschaft "Comments" fest und fügen Sie dann ein INFO-Feld ein, um den Wert dieser Eigenschaft anzuzeigen.
doc.BuiltInDocumentProperties.Comments = "My comment";
FieldInfo field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.Update();

Assert.AreEqual(" INFO  Comments", field.GetFieldCode());
Assert.AreEqual("My comment", field.Result);

builder.Writeln();

// Festlegen eines Werts für die NewValue-Eigenschaft des Felds und Aktualisieren
// Das Feld überschreibt auch die entsprechende eingebaute Eigenschaft mit dem neuen Wert.
field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.NewValue = "New comment";
field.Update();

Assert.AreEqual(" INFO  Comments \"New comment\"", field.GetFieldCode());
Assert.AreEqual("New comment", field.Result);
Assert.AreEqual("New comment", doc.BuiltInDocumentProperties.Comments);

doc.Save(ArtifactsDir + "Field.INFO.docx");
```

### Siehe auch

* class [FieldInfo](../)
* namensraum [Aspose.Words.Fields](../../fieldinfo/)
* Montage [Aspose.Words](../../../)


