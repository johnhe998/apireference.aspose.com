---
title: StyleCollection.AddCopy
second_title: Справочник по API Aspose.Words для .NET
description: StyleCollection метод. Копирует стиль в эту коллекцию.
type: docs
weight: 70
url: /ru/net/aspose.words/stylecollection/addcopy/
---
## StyleCollection.AddCopy method

Копирует стиль в эту коллекцию.

```csharp
public Style AddCopy(Style style)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| style | Style | Стиль для копирования. |

### Возвращаемое значение

Скопированный стиль готов к использованию.

### Примечания

Копируемый стиль может принадлежать как одному, так и разным документам.

Связанный стиль копируется.

Этот метод не копирует базовые стили.

Если коллекция уже содержит стиль с таким именем, то новое имя создается автоматически путем добавления суффикса «_number», начиная с 0, например, «Обычный_0», «Заголовок 1_1» и т. д. Использовать[`Name`](../../style/name/) setter для изменения имени импортированного стиля.

### Примеры

Показывает, как импортировать стиль из одного документа в другой документ.

```csharp
Document srcDoc = new Document();

// Создаем собственный стиль для исходного документа.
Style srcStyle = srcDoc.Styles.Add(StyleType.Paragraph, "MyStyle");
srcStyle.Font.Color = Color.Red;

// Импорт пользовательского стиля исходного документа в целевой документ.
Document dstDoc = new Document();
Style newStyle = dstDoc.Styles.AddCopy(srcStyle);

// Внешний вид импортированного стиля идентичен исходному стилю.
Assert.AreEqual("MyStyle", newStyle.Name);
Assert.AreEqual(Color.Red.ToArgb(), newStyle.Font.Color.ToArgb());
```

Показывает, как клонировать стиль документа.

```csharp
Document doc = new Document();

// Метод AddCopy создает копию указанного стиля и
// автоматически генерирует новое имя для стиля, например "Заголовок 1_0".
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// Используйте свойство «Имя» стиля, чтобы изменить идентифицирующее имя стиля.
newStyle.Name = "My Heading 1";

// Наш документ теперь имеет два идентичных стиля с разными именами.
// Изменение настроек одного из стилей не влияет на другой.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### Смотрите также

* class [Style](../../style/)
* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)


