---
title: Enum EmphasisMark
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.EmphasisMark перечисление. Определяет возможные типы выделения.
type: docs
weight: 1310
url: /ru/net/aspose.words/emphasismark/
---
## EmphasisMark enumeration

Определяет возможные типы выделения.

```csharp
public enum EmphasisMark
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Без выделения. |
| OverSolidCircle | `1` | Знак выделения — это сплошной черный кружок, отображаемый над текстом. |
| OverComma | `2` | Знак выделения — это символ запятой, отображаемый над текстом. |
| OverWhiteCircle | `3` | Знак выделения — это пустой белый кружок, отображаемый над текстом. |
| UnderSolidCircle | `4` | Знак выделения — это сплошной черный кружок, отображаемый под текстом. |

### Примеры

Показывает, как добавить дополнительный символ, отображаемый над/под глифом.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Возможные типы знака ударения:
// https://apireference.aspose.com/words/net/aspose.words/emphasismark
builder.Font.EmphasisMark = emphasisMark; 

builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");

builder.Document.Save(ArtifactsDir + "Fonts.SetEmphasisMark.docx");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


