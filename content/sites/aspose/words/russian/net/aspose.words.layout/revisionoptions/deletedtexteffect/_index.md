---
title: RevisionOptions.DeletedTextEffect
second_title: Справочник по API Aspose.Words для .NET
description: RevisionOptions свойство. Позволяет указать эффект который будет применяться к удаленному контентуDeletion . Значение по умолчаниюStrikeThrough
type: docs
weight: 30
url: /ru/net/aspose.words.layout/revisionoptions/deletedtexteffect/
---
## RevisionOptions.DeletedTextEffect property

Позволяет указать эффект, который будет применяться к удаленному контентуDeletion . Значение по умолчанию:StrikeThrough

```csharp
public RevisionTextEffect DeletedTextEffect { get; set; }
```

### Примеры

Показывает, как изменить внешний вид редакций.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Получить объект RevisionOptions, управляющий внешним видом ревизий.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Отображение ревизий вставки зеленым цветом и курсивом.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Отображение удаленных ревизий красным и полужирным шрифтом.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Один и тот же текст появится дважды в ревизии движения:
// один раз в пункте отправления и один раз в пункте прибытия.
// Визуализируем текст перемещенной версии желтым цветом с двойным перечеркиванием
// и дважды подчеркнутый синим цветом ревизию, к которой был перемещен.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Редактирование формата темно-красным и полужирным шрифтом.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Поместите толстую темно-синюю полосу в левой части страницы рядом со строками, затронутыми изменениями.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Показать метки исправления и исходный текст.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Получить перемещение, удаление, исправления форматирования и комментарии для отображения в зеленых выносках
// в правой части страницы.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Эти функции применимы только к таким форматам, как .pdf или .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Смотрите также

* enum [RevisionTextEffect](../../revisiontexteffect/)
* class [RevisionOptions](../)
* пространство имен [Aspose.Words.Layout](../../revisionoptions/)
* сборка [Aspose.Words](../../../)


