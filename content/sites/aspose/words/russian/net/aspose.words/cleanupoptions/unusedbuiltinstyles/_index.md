---
title: CleanupOptions.UnusedBuiltinStyles
second_title: Справочник по API Aspose.Words для .NET
description: CleanupOptions свойство. Указывает что неиспользуемыйBuiltIn стили должны быть удалены из документа.
type: docs
weight: 30
url: /ru/net/aspose.words/cleanupoptions/unusedbuiltinstyles/
---
## CleanupOptions.UnusedBuiltinStyles property

Указывает, что неиспользуемый[`BuiltIn`](../../style/builtin/) стили должны быть удалены из документа.

```csharp
public bool UnusedBuiltinStyles { get; set; }
```

### Примеры

Показывает, как удалить все неиспользуемые пользовательские стили из документа.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// В сочетании со встроенными стилями документ теперь имеет восемь стилей.
// Пользовательский стиль помечается как «используемый», пока в документе есть какой-либо текст
// отформатировано в этом стиле. Это означает, что 4 добавленных нами стиля в настоящее время не используются.
Assert.AreEqual(8, doc.Styles.Count);

// Применение пользовательского стиля символов, а затем пользовательского стиля списка. При этом они будут помечены как «использованные».
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

// Теперь есть один неиспользуемый стиль символов и один неиспользуемый стиль списка.
// Метод Cleanup(), сконфигурированный с объектом CleanupOptions, может нацеливаться на неиспользуемые стили и удалять их.
CleanupOptions cleanupOptions = new CleanupOptions
{
    UnusedLists = true, UnusedStyles = true, UnusedBuiltinStyles = true
};

doc.Cleanup(cleanupOptions);

Assert.AreEqual(4, doc.Styles.Count);

// Удаление каждого узла, к которому применен пользовательский стиль, снова помечает его как «неиспользуемый». 
// Повторно запустите метод Cleanup, чтобы удалить их.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup(cleanupOptions);

Assert.AreEqual(2, doc.Styles.Count);
```

### Смотрите также

* class [CleanupOptions](../)
* пространство имен [Aspose.Words](../../cleanupoptions/)
* сборка [Aspose.Words](../../../)


