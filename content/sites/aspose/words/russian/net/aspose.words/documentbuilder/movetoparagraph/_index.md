---
title: DocumentBuilder.MoveToParagraph
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Перемещает курсор на абзац в текущем разделе.
type: docs
weight: 540
url: /ru/net/aspose.words/documentbuilder/movetoparagraph/
---
## DocumentBuilder.MoveToParagraph method

Перемещает курсор на абзац в текущем разделе.

```csharp
public void MoveToParagraph(int paragraphIndex, int characterIndex)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| paragraphIndex | Int32 | Индекс абзаца, к которому нужно перейти. |
| characterIndex | Int32 | Индекс символа внутри абзаца. Отрицательное значение позволяет указать позицию от конца абзаца. Используйте -1, чтобы перейти в конец абзаца of . |

### Примечания

Навигация выполняется внутри текущей истории текущего раздела. То есть, если вы переместили курсор к основному заголовку первого раздела, , то параграфИндекс указывает индекс абзаца внутри этого заголовка этого раздела.

Когда paraIndex больше или равен 0, он указывает индекс from начала раздела, где 0 является первым абзацем. Когда paraIndex меньше 0, , он указывает индекс с конца раздела, где -1 является последним абзацем.

### Примеры

Показывает, как переместить позицию курсора конструктора в указанный абзац.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(22, paragraphs.Count);

// Создать конструктор документов для редактирования документа. Курсор строителя,
// это точка, в которой он будет вставлять новые узлы, когда мы вызываем его методы построения документа,
// сейчас находится в начале документа.
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Перемещение этого курсора в другой абзац поместит этот курсор перед этим абзацем.
builder.MoveToParagraph(2, 0);
// Любой новый контент, который мы добавляем, будет вставлен в эту точку.
builder.Writeln("This is a new third paragraph. ");
```

### Смотрите также

* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


