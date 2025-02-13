---
title: Document.AutomaticallyUpdateStyles
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Получает или задает флаг указывающий обновляются ли стили в документе в соответствии со стилями в прикрепленном шаблоне каждый раз когда документ открывается в MS Word.
type: docs
weight: 30
url: /ru/net/aspose.words/document/automaticallyupdatestyles/
---
## Document.AutomaticallyUpdateStyles property

Получает или задает флаг, указывающий, обновляются ли стили в документе в соответствии со стилями в прикрепленном шаблоне каждый раз, когда документ открывается в MS Word.

```csharp
public bool AutomaticallyUpdateStyles { get; set; }
```

### Примеры

Показывает, как прикрепить шаблон к документу.

```csharp
Document doc = new Document();

// Документы Microsoft Word по умолчанию поставляются с прикрепленным шаблоном с именем «Normal.dotm».
// Для пустых документов Aspose.Words нет шаблона по умолчанию.
Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Прикрепите шаблон, затем установите флаг, чтобы применить изменения стиля
// внутри шаблона для стилей в нашем документе.
doc.AttachedTemplate = MyDir + "Business brochure.dotx";
doc.AutomaticallyUpdateStyles = true;

doc.Save(ArtifactsDir + "Document.AutomaticallyUpdateStyles.docx");
```

Показывает, как задать шаблон по умолчанию для документов, к которым нет прикрепленных шаблонов.

```csharp
Document doc = new Document();

// Включить автоматическое обновление стиля, но не прикреплять шаблонный документ.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Так как документа-шаблона нет, в документе негде было отслеживать изменения стилей.
// Используйте объект SaveOptions для автоматической установки шаблона
// если документа, который мы сохраняем, нет.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


