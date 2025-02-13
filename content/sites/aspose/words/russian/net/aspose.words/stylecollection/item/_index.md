---
title: StyleCollection.Item
second_title: Справочник по API Aspose.Words для .NET
description: StyleCollection свойство. Получает стиль по имени или псевдониму.
type: docs
weight: 50
url: /ru/net/aspose.words/stylecollection/item/
---
## StyleCollection indexer (1 of 3)

Получает стиль по имени или псевдониму.

```csharp
public Style this[string name] { get; }
```

### Примечания

С учетом регистра, возвращает ноль, если стиль с заданным именем не найден.

Если это английское имя встроенного стиля, которого еще не существует, он создается автоматически.

### Примеры

Показывает, когда пересчитывать макет страницы документа.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Сохранение документа в PDF, изображение или печать в первый раз автоматически
// кэшируем макет документа на его страницах.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// Измените документ каким-либо образом.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // В текущей версии Aspose.Words изменение документа не приводит к автоматическому перестроению
// кешированный макет страницы. Если мы хотим кэшированный макет
// чтобы оставаться в курсе, нам нужно будет обновить его вручную.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### Смотрите также

* class [Style](../../style/)
* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)

---

## StyleCollection indexer (2 of 3)

Получает встроенный стиль по его независимому от языкового стандарта идентификатору.

```csharp
public Style this[StyleIdentifier sti] { get; }
```

| Параметр | Описание |
| --- | --- |
| sti | А[`StyleIdentifier`](../../styleidentifier/) значение, указывающее встроенный стиль для извлечения. |

### Примечания

При обращении к еще не существующему стилю автоматически создает его.

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

* class [Style](../../style/)
* enum [StyleIdentifier](../../styleidentifier/)
* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)

---

## StyleCollection indexer (3 of 3)

Получает стиль по индексу.

```csharp
public Style this[int index] { get; }
```

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

* class [Style](../../style/)
* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)


