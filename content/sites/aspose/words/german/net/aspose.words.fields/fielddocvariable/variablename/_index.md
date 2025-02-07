---
title: FieldDocVariable.VariableName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldDocVariable eigendom. Ruft den Namen der abzurufenden Dokumentvariablen ab oder legt ihn fest.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

Ruft den Namen der abzurufenden Dokumentvariablen ab oder legt ihn fest.

```csharp
public string VariableName { get; set; }
```

### Beispiele

Zeigt, wie DOCPROPERTY-Felder verwendet werden, um Dokumenteigenschaften und -variablen anzuzeigen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Im Folgenden finden Sie zwei Möglichkeiten zur Verwendung von DOCPROPERTY-Feldern.
// 1 - Zeigt eine eingebaute Eigenschaft an:
// Legen Sie einen benutzerdefinierten Wert für die integrierte Eigenschaft "Kategorie" fest und fügen Sie dann ein DOCPROPERTY-Feld ein, das darauf verweist.
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - Eine benutzerdefinierte Dokumentvariable anzeigen:
// Eine benutzerdefinierte Variable definieren und diese Variable dann mit einem DOCPROPERTY-Feld referenzieren.
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### Siehe auch

* class [FieldDocVariable](../)
* namensraum [Aspose.Words.Fields](../../fielddocvariable/)
* Montage [Aspose.Words](../../../)


