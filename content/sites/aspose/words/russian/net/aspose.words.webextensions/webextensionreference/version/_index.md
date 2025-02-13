---
title: WebExtensionReference.Version
second_title: Справочник по API Aspose.Words для .NET
description: WebExtensionReference свойство. Указывает версию вебрасширения.
type: docs
weight: 50
url: /ru/net/aspose.words.webextensions/webextensionreference/version/
---
## WebExtensionReference.Version property

Указывает версию веб-расширения.

```csharp
public string Version { get; set; }
```

### Примеры

Показывает, как добавить веб-расширение в документ.

```csharp
Document doc = new Document();

// Создаем панель задач с надстройкой "MyScript", которая будет использоваться документом,
// затем установите его местоположение по умолчанию.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// Если в одном и том же месте закрепления есть несколько панелей задач, мы можем установить этот индекс, чтобы упорядочить их.
myScriptTaskPane.Row = 1;

// Создайте надстройку под названием «MyScript Math Sample», внутри которой будет отображаться панель задач.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Задаем эталонные параметры хранилища приложений для нашей надстройки, например идентификатор.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Разрешить пользователю взаимодействовать с надстройкой.
webExtension.IsFrozen = false;

// Мы можем получить доступ к веб-расширению в Microsoft Word через Developer -> Надстройки.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Сразу удалить все панели задач веб-расширения, как показано ниже.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Смотрите также

* class [WebExtensionReference](../)
* пространство имен [Aspose.Words.WebExtensions](../../webextensionreference/)
* сборка [Aspose.Words](../../../)


