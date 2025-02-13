---
title: ParagraphFormat.SuppressAutoHyphens
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Указывает должен ли текущий абзац быть освобожден от любых переносов которые применяются в настройках документа.
type: docs
weight: 360
url: /ru/net/aspose.words/paragraphformat/suppressautohyphens/
---
## ParagraphFormat.SuppressAutoHyphens property

Указывает, должен ли текущий абзац быть освобожден от любых переносов, которые применяются в настройках документа.

```csharp
public bool SuppressAutoHyphens { get; set; }
```

### Примеры

Показывает, как подавить переносы для абзаца.

```csharp
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// Открыть документ, содержащий текст с локалью, соответствующей локали нашего словаря.
// Когда мы сохраняем этот документ в фиксированном формате сохранения страницы, в его тексте будут переносы.
Document doc = new Document(MyDir + "German text.docx");

// Мы можем установить для свойства "SuppressAutoHyphens" значение "true", чтобы отключить переносы
// для определенного абзаца, оставляя его включенным для остальной части документа.
// Значение по умолчанию для этого свойства "false",
// что означает, что каждый абзац по умолчанию использует переносы, если таковые имеются.
doc.FirstSection.Body.FirstParagraph.ParagraphFormat.SuppressAutoHyphens = suppressAutoHyphens;

doc.Save(ArtifactsDir + "ParagraphFormat.SuppressHyphens.pdf");
```

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


