---
title: Document.RemoveMacros
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Удаляет все макросы проект VBA а также панели инструментов и настройки команд из документа.
type: docs
weight: 650
url: /ru/net/aspose.words/document/removemacros/
---
## Document.RemoveMacros method

Удаляет все макросы (проект VBA), а также панели инструментов и настройки команд из документа.

```csharp
public void RemoveMacros()
```

### Примечания

Удаляя все макросы из документа, вы гарантируете, что документ не содержит макровирусов.

### Примеры

Показывает, как удалить все макросы из документа.

```csharp
Document doc = new Document(MyDir + "Macro.docm");

Assert.IsTrue(doc.HasMacros);
Assert.AreEqual("Project", doc.VbaProject.Name);

// Удаляем проект VBA документа вместе со всеми его макросами.
doc.RemoveMacros();

Assert.IsFalse(doc.HasMacros);
Assert.Null(doc.VbaProject);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


