---
title: VbaModuleCollection.Count
second_title: Справочник по API Aspose.Words для .NET
description: VbaModuleCollection свойство. Возвращает количество модулей VBA в коллекции.
type: docs
weight: 10
url: /ru/net/aspose.words.vba/vbamodulecollection/count/
---
## VbaModuleCollection.Count property

Возвращает количество модулей VBA в коллекции.

```csharp
public int Count { get; }
```

### Примеры

Показывает, как получить доступ к информации о проекте документа VBA.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Проект VBA содержит набор модулей VBA.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Установить новый исходный код для модуля VBA. Вы можете получить доступ к модулям VBA в коллекции либо по индексу, либо по имени.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Удалить модуль из коллекции.
vbaModules.Remove(vbaModules[2]);
```

### Смотрите также

* class [VbaModuleCollection](../)
* пространство имен [Aspose.Words.Vba](../../vbamodulecollection/)
* сборка [Aspose.Words](../../../)


