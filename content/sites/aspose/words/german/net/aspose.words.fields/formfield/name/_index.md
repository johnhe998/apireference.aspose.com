---
title: FormField.Name
second_title: Aspose.Words für .NET-API-Referenz
description: FormField eigendom. Ruft den Formularfeldnamen ab oder legt ihn fest.
type: docs
weight: 130
url: /de/net/aspose.words.fields/formfield/name/
---
## FormField.Name property

Ruft den Formularfeldnamen ab oder legt ihn fest.

```csharp
public string Name { get; set; }
```

### Bemerkungen

Microsoft Word erlaubt Zeichenfolgen mit höchstens 20 Zeichen.

### Beispiele

Zeigt, wie ein Kombinationsfeld eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Fügen Sie ein Kombinationsfeld ein, das es einem Benutzer ermöglicht, eine Option aus einer Sammlung von Zeichenfolgen auszuwählen.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// Das Formularfeld erscheint in Form eines „select“-HTML-Tags.
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Siehe auch

* class [FormField](../)
* namensraum [Aspose.Words.Fields](../../formfield/)
* Montage [Aspose.Words](../../../)


