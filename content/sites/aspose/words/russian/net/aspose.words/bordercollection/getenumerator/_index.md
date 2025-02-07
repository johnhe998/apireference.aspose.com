---
title: BorderCollection.GetEnumerator
second_title: Справочник по API Aspose.Words для .NET
description: BorderCollection метод. Возвращает объект перечислителя который можно использовать для перебора всех границ в коллекции.
type: docs
weight: 160
url: /ru/net/aspose.words/bordercollection/getenumerator/
---
## BorderCollection.GetEnumerator method

Возвращает объект перечислителя, который можно использовать для перебора всех границ в коллекции.

```csharp
public IEnumerator<Border> GetEnumerator()
```

### Примеры

Показывает, как перебирать и редактировать все границы в объекте формата абзаца.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Настройте параметры формата абзаца компоновщика, чтобы создать зеленую волнистую границу со всех сторон.
BorderCollection borders = builder.ParagraphFormat.Borders;

using (IEnumerator<Border> enumerator = borders.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Border border = enumerator.Current;
        border.Color = Color.Green;
        border.LineStyle = LineStyle.Wave;
        border.LineWidth = 3;
    }
}

// Вставить абзац. Наши настройки границы будут определять внешний вид ее границы.
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "BorderCollection.GetBordersEnumerator.docx");
```

### Смотрите также

* class [Border](../../border/)
* class [BorderCollection](../)
* пространство имен [Aspose.Words](../../bordercollection/)
* сборка [Aspose.Words](../../../)


