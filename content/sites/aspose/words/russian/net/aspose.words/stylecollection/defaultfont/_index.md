---
title: StyleCollection.DefaultFont
second_title: Справочник по API Aspose.Words для .NET
description: StyleCollection свойство. Получает форматирование текста документа по умолчанию.
type: docs
weight: 20
url: /ru/net/aspose.words/stylecollection/defaultfont/
---
## StyleCollection.DefaultFont property

Получает форматирование текста документа по умолчанию.

```csharp
public Font DefaultFont { get; }
```

### Примечания

Обратите внимание, что значения по умолчанию для всего документа были введены в Microsoft Word 2007 и полностью поддерживаются в форматах OOXML (Docx) only. Более ранние форматы документов имеют ограниченную поддержку этой функции и могут сохранять только имена шрифтов.

### Примеры

Показывает, как добавить стиль в коллекцию стилей документа.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Задаем параметры по умолчанию для новых стилей, которые позже мы можем добавить в эту коллекцию.
styles.DefaultFont.Name = "Courier New";

// Если мы добавим стиль "StyleType.Paragraph", коллекция применит значения
// его свойство "DefaultParagraphFormat" к свойству "ParagraphFormat" стиля.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Добавьте стиль, а затем убедитесь, что он имеет настройки по умолчанию.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Смотрите также

* class [Font](../../font/)
* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)


