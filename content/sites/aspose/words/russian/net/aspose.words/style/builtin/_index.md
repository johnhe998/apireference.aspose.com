---
title: Style.BuiltIn
second_title: Справочник по API Aspose.Words для .NET
description: Style свойство. Истинно если этот стиль является одним из встроенных стилей в MS Word.
type: docs
weight: 30
url: /ru/net/aspose.words/style/builtin/
---
## Style.BuiltIn property

Истинно, если этот стиль является одним из встроенных стилей в MS Word.

```csharp
public bool BuiltIn { get; }
```

### Примеры

Показывает, как отличить пользовательские стили от встроенных стилей.

```csharp
Document doc = new Document();

// Когда мы создаем документ с помощью Microsoft Word или программно с помощью Aspose.Words,
// документ будет поставляться с набором стилей, которые можно применить к его тексту, чтобы изменить его внешний вид.
// Мы можем получить доступ к этим встроенным стилям через коллекцию «Стили» документа.
// Все эти стили будут иметь флаг "BuiltIn", установленный на "true".
Style style = doc.Styles["Emphasis"];

Assert.True(style.BuiltIn);

// Создадим собственный стиль и добавим его в коллекцию.
 // Пользовательские стили, такие как этот, будут иметь флаг «Встроенный», установленный на «ложь».
style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Navy;
style.Font.Name = "Courier New";

Assert.False(style.BuiltIn);
```

### Смотрите также

* class [Style](../)
* пространство имен [Aspose.Words](../../style/)
* сборка [Aspose.Words](../../../)


