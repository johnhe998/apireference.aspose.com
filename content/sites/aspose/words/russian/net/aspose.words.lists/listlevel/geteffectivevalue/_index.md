---
title: ListLevel.GetEffectiveValue
second_title: Справочник по API Aspose.Words для .NET
description: ListLevel метод. Сообщает строковое представлениеListLevel объект для указанного index элемента списка. Параметры определяютNumberStyle и необязательный формат string  используемый когдаCustom указан.
type: docs
weight: 190
url: /ru/net/aspose.words.lists/listlevel/geteffectivevalue/
---
## ListLevel.GetEffectiveValue method

Сообщает строковое представление[`ListLevel`](../) объект для указанного index элемента списка. Параметры определяют[`NumberStyle`](../../../aspose.words/numberstyle/) и необязательный формат string , используемый, когдаCustom указан.

```csharp
public static string GetEffectiveValue(int index, NumberStyle numberStyle, 
    string customNumberStyleFormat)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| index | Int32 | Индекс элемента списка (должен быть в диапазоне от 1 до 32767). |
| numberStyle | NumberStyle | [`NumberStyle`](../../../aspose.words/numberstyle/) принадлежащий[`ListLevel`](../) объект. |
| customNumberStyleFormat | String | Необязательная строка формата, используемая приCustom указан (например, "a, ç, ĝ, ..."). В других случаях этот параметр должен быть нулевым или пустым. |

### Возвращаемое значение

Строковое представление[`ListLevel`](../) объект, описанный параметром numberStyle и параметром customNumberStyleFormat, в элементе списка в позиции, определяемой параметром index.

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentException | customNumberStyleFormat имеет значение null или пустое, если numberStyle является пользовательским.-или- customNumberStyleFormat не является нулевым или пустым, если numberStyle не является пользовательским.-или- customNumberStyleFormat является недопустимым. |
| ArgumentOutOfRangeException | индекс вне допустимого диапазона. |

### Примеры

Показывает, как получить формат для списка с пользовательским стилем чисел.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Мы можем получить значение для указанного индекса элемента списка.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Смотрите также

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [ListLevel](../)
* пространство имен [Aspose.Words.Lists](../../listlevel/)
* сборка [Aspose.Words](../../../)


