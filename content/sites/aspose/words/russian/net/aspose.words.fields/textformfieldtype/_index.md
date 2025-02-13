---
title: Enum TextFormFieldType
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fields.TextFormFieldType перечисление. Определяет тип поля текстовой формы.
type: docs
weight: 2590
url: /ru/net/aspose.words.fields/textformfieldtype/
---
## TextFormFieldType enumeration

Определяет тип поля текстовой формы.

```csharp
public enum TextFormFieldType
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Regular | `0` | Поле текстовой формы может содержать любой текст. |
| Number | `1` | Поле текстовой формы может содержать только числа. |
| Date | `2` | Поле текстовой формы может содержать только действительное значение даты. |
| CurrentDate | `3` | Значением поля текстовой формы является текущая дата обновления поля. |
| CurrentTime | `4` | Значением поля текстовой формы является текущее время, когда поле обновляется. |
| Calculated | `5` | Значение поля текстовой формы вычисляется из выражения, указанного в [`TextInputDefault`](../formfield/textinputdefault/) свойство. |

### Примеры

Показывает, как создавать поля формы.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Поля формы — это объекты в документе, с которыми пользователь может взаимодействовать, получая запрос на ввод значений.
// Мы можем создать их с помощью конструктора документов, и ниже приведены два способа сделать это.
// 1 - Основной ввод текста:
builder.InsertTextInput("My text input", TextFormFieldType.Regular, 
    "", "Enter your name here", 30);

// 2 - Поле со списком с текстом подсказки и диапазоном возможных значений:
string[] items =
{
    "-- Select your favorite footwear --", "Sneakers", "Oxfords", "Flip-flops", "Other"
};

builder.InsertParagraph();
builder.InsertComboBox("My combo box", items, 0);

builder.Document.Save(ArtifactsDir + "DocumentBuilder.CreateForm.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Fields](../../aspose.words.fields/)
* сборка [Aspose.Words](../../)


