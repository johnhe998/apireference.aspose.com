---
title: FormField.Type
second_title: Справочник по API Aspose.Words для .NET
description: FormField свойство. Возвращает тип поля формы.
type: docs
weight: 220
url: /ru/net/aspose.words.fields/formfield/type/
---
## FormField.Type property

Возвращает тип поля формы.

```csharp
public FieldType Type { get; }
```

### Примеры

Показывает, как вставить поле со списком.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Вставьте поле со списком, которое позволит пользователю выбрать вариант из набора строк.
FormField comboBox = builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

Assert.AreEqual("MyComboBox", comboBox.Name);
Assert.AreEqual(FieldType.FieldFormDropDown, comboBox.Type);
Assert.AreEqual("Apple", comboBox.Result);

// Поле формы появится в виде html-тега select.
doc.Save(ArtifactsDir + "FormFields.Create.html");
```

### Смотрите также

* enum [FieldType](../../fieldtype/)
* class [FormField](../)
* пространство имен [Aspose.Words.Fields](../../formfield/)
* сборка [Aspose.Words](../../../)


