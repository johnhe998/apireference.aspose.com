---
title: FormField.Type
second_title: Aspose.Words för .NET API Referens
description: FormField fast egendom. Returnerar formulärfältstypen.
type: docs
weight: 220
url: /sv/net/aspose.words.fields/formfield/type/
---
## FormField.Type property

Returnerar formulärfältstypen.

```csharp
public FieldType Type { get; }
```

### Exempel

Visar hur man infogar en kombinationsruta.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Infoga en kombinationsruta som låter en användare välja ett alternativ från en samling strängar.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// Formulärfältet kommer att visas i form av en "select" html-tagg.
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Se även

* enum [FieldType](../../fieldtype/)
* class [FormField](../)
* namnutrymme [Aspose.Words.Fields](../../formfield/)
* hopsättning [Aspose.Words](../../../)


