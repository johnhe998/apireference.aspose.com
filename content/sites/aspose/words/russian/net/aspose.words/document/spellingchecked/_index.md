---
title: Document.SpellingChecked
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Возвращает истинный если документ проверен на орфографию.
type: docs
weight: 390
url: /ru/net/aspose.words/document/spellingchecked/
---
## Document.SpellingChecked property

Возвращает **истинный** если документ проверен на орфографию.

```csharp
public bool SpellingChecked { get; set; }
```

### Примечания

Чтобы перепроверить орфографию в документе, установите для этого свойства значение **ЛОЖЬ** .

### Примеры

Показывает, как настроить проверку орфографии или грамматики.

```csharp
Document doc = new Document();

// Строка с орфографическими ошибками.
doc.FirstSection.Body.FirstParagraph.Runs.Add(new Run(doc, "The speeling in this documentz is all broked."));

 // Проверка орфографии/грамматики начинается, если мы устанавливаем для свойств значение false.
// Мы можем увидеть все ошибки в Microsoft Word через Обзор -> Орфография & Грамматика.
// Обратите внимание, что Microsoft Word не запускает автоматическую проверку грамматики/орфографии для форматов документов DOC и RTF.
doc.SpellingChecked = checkSpellingGrammar;
doc.GrammarChecked = checkSpellingGrammar;

doc.Save(ArtifactsDir + "Document.SpellingOrGrammar.docx");
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


