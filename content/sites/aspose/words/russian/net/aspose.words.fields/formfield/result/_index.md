---
title: FormField.Result
second_title: Справочник по API Aspose.Words для .NET
description: FormField свойство. Получает или задает строку представляющую результат этого поля формы.
type: docs
weight: 170
url: /ru/net/aspose.words.fields/formfield/result/
---
## FormField.Result property

Получает или задает строку, представляющую результат этого поля формы.

```csharp
public string Result { get; set; }
```

### Примечания

Для поля текстовой формы результатом является текст, который находится в поле.

Для поля формы флажка результат может быть «1» или «0», чтобы указать, отмечен или не отмечен.

Для раскрывающегося поля формы результатом является строка, выбранная в раскрывающемся списке.

Параметр`Result` для поля текстовой формы не применяется текстовый формат , указанный в[`TextInputFormat`](../textinputformat/) . Если вы хотите установить значение и применить формат , используйте[`SetTextInputValue`](../settextinputvalue/) метод.

Для поля текстовой формы[`TextInputDefault`](../textinputdefault/) значение применяется , если*value* является`нулевой`.

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

* class [FormField](../)
* пространство имен [Aspose.Words.Fields](../../formfield/)
* сборка [Aspose.Words](../../../)


