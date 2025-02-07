---
title: Font.NoProofing
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Истина если отформатированные символы не должны проверяться на орфографию.
type: docs
weight: 280
url: /ru/net/aspose.words/font/noproofing/
---
## Font.NoProofing property

Истина, если отформатированные символы не должны проверяться на орфографию.

```csharp
public bool NoProofing { get; set; }
```

### Примеры

Показывает, как предотвратить проверку орфографии текста программой Microsoft Word.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Обычно Microsoft Word подчеркивает орфографические ошибки неровным красным подчеркиванием.
// Мы можем снять флаг "NoProofing", чтобы создать часть текста,
// обходит проверку орфографии, полностью отключая ее.
builder.Font.NoProofing = true;

builder.Writeln("Proofing has been disabled, so these spelking errrs will not display red lines underneath.");

doc.Save(ArtifactsDir + "Font.NoProofing.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


