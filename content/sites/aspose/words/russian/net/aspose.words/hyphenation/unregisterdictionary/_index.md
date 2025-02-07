---
title: Hyphenation.UnregisterDictionary
second_title: Справочник по API Aspose.Words для .NET
description: Hyphenation метод. Отменяет регистрацию словаря переносов для указанного языка.
type: docs
weight: 50
url: /ru/net/aspose.words/hyphenation/unregisterdictionary/
---
## Hyphenation.UnregisterDictionary method

Отменяет регистрацию словаря переносов для указанного языка.

Это отличается от регистрации нулевого словаря. Отмена регистрации словаря включает обратный вызов для указанного языка.

```csharp
public static void UnregisterDictionary(string language)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| language | String | Название языка, например "en-US". См. документацию .NET для «имени культуры» и RFC 4646 для получения подробной информации. |

### Примеры

Показывает, как зарегистрировать словарь переносов.

```csharp
// Словарь расстановки переносов содержит список строк, определяющих правила расстановки переносов для языка словаря.
// Когда документ содержит строки текста, в которых слово можно разделить и продолжить на следующей строке,
// перенос будет искать в списке строк словаря подстроки этого слова.
// Если словарь содержит подстроку, то перенос разделит слово на две строки
// по подстроке и добавляем дефис к первой половине.
// Зарегистрировать файл словаря из локальной файловой системы в локали "de-CH".
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// Открываем документ, содержащий текст с локалью, соответствующей локали нашего словаря,
// и сохранить его в формате сохранения с фиксированной страницей. Текст в этом документе будет разделен через дефис.
Document doc = new Document(MyDir + "German text.docx");

Assert.True(doc.FirstSection.Body.FirstParagraph.Runs.OfType<Run>().All(
    r => r.Font.LocaleId == new CultureInfo("de-CH").LCID));

doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Registered.pdf");

// Перезагружаем документ после отмены регистрации словаря,
// и сохраните его в другой PDF-файл, в котором не будет текста с переносами.
Hyphenation.UnregisterDictionary("de-CH");

Assert.False(Hyphenation.IsDictionaryRegistered("de-CH"));

doc = new Document(MyDir + "German text.docx");
doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Unregistered.pdf");
```

### Смотрите также

* class [Hyphenation](../)
* пространство имен [Aspose.Words](../../hyphenation/)
* сборка [Aspose.Words](../../../)


