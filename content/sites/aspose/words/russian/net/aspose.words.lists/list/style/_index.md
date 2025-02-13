---
title: List.Style
second_title: Справочник по API Aspose.Words для .NET
description: List свойство. Получает стиль списка на который ссылается или определяет этот список.
type: docs
weight: 80
url: /ru/net/aspose.words.lists/list/style/
---
## List.Style property

Получает стиль списка, на который ссылается или определяет этот список.

```csharp
public Style Style { get; }
```

### Примечания

Если этот список не связан со стилем списка, свойство вернет значение null.

Список может быть ссылкой на стиль списка, в этом случае[`IsListStyleReference`](../isliststylereference/) будет правдой.

Список может быть определением стиля списка, в этом случае[`IsListStyleDefinition`](../isliststyledefinition/) будет правдой. Такой список нельзя применить к абзацам документа напрямую.

### Примеры

Показывает, как создать стиль списка и использовать его в документе.

```csharp
Document doc = new Document();

// Список позволяет нам организовывать и оформлять наборы абзацев префиксными символами и отступами.
// Мы можем создавать вложенные списки, увеличивая уровень отступа. 
// Мы можем начать и закончить список, используя свойство "ListFormat" конструктора документов. 
// Каждый абзац, который мы добавляем между началом и концом списка, станет элементом списка.
// Мы можем содержать весь объект List в стиле.
Style listStyle = doc.Styles.Add(StyleType.List, "MyListStyle");

List list1 = listStyle.List;

Assert.True(list1.IsListStyleDefinition);
Assert.False(list1.IsListStyleReference);
Assert.True(list1.IsMultiLevel);
Assert.AreEqual(listStyle, list1.Style);

// Изменяем внешний вид всех уровней списка в нашем списке.
foreach (ListLevel level in list1.ListLevels)
{
    level.Font.Name = "Verdana";
    level.Font.Color = Color.Blue;
    level.Font.Bold = true;
}

DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Using list style first time:");

// Создать другой список из списка в стиле.
List list2 = doc.Lists.Add(listStyle);

Assert.False(list2.IsListStyleDefinition);
Assert.True(list2.IsListStyleReference);
Assert.AreEqual(listStyle, list2.Style);

// Добавляем несколько элементов списка, которые будут отформатированы в нашем списке.
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Writeln("Using list style second time:");

// Создать и применить другой список на основе стиля списка.
List list3 = doc.Lists.Add(listStyle);
builder.ListFormat.List = list3;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateAndUseListStyle.docx");
```

### Смотрите также

* class [Style](../../../aspose.words/style/)
* class [List](../)
* пространство имен [Aspose.Words.Lists](../../list/)
* сборка [Aspose.Words](../../../)


