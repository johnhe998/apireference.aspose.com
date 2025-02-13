---
title: FieldDocVariable.VariableName
second_title: Справочник по API Aspose.Words для .NET
description: FieldDocVariable свойство. Получает или задает имя переменной документа для извлечения.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

Получает или задает имя переменной документа для извлечения.

```csharp
public string VariableName { get; set; }
```

### Примеры

Показывает, как использовать поля DOCPROPERTY для отображения свойств и переменных документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ниже приведены два способа использования полей DOCPROPERTY.
// 1 - Показать встроенное свойство:
// Установите пользовательское значение для встроенного свойства «Категория», затем вставьте поле DOCPROPERTY, которое на него ссылается.
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - Отобразить пользовательскую переменную документа:
// Определяем пользовательскую переменную, затем ссылаемся на эту переменную с помощью поля DOCPROPERTY.
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### Смотрите также

* class [FieldDocVariable](../)
* пространство имен [Aspose.Words.Fields](../../fielddocvariable/)
* сборка [Aspose.Words](../../../)


