---
title: Enum TableAlignment
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Tables.TableAlignment перечисление. Указывает выравнивание для встроенной таблицы.
type: docs
weight: 6050
url: /ru/net/aspose.words.tables/tablealignment/
---
## TableAlignment enumeration

Указывает выравнивание для встроенной таблицы.

```csharp
public enum TableAlignment
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Left | `0` | Таблица выровнена по левому краю. |
| Center | `1` | Таблица центрирована. |
| Right | `2` | Таблица выровнена по правому краю. |

### Примеры

Показывает, как применить границу контура к таблице.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Выравниваем таблицу по центру страницы.
table.Alignment = TableAlignment.Center;

// Очистить все существующие границы и затенение из таблицы.
table.ClearBorders();
table.ClearShading();

// Добавляем зеленые рамки к контуру таблицы.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Заливаем ячейки светло-зеленым сплошным цветом.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Tables](../../aspose.words.tables/)
* сборка [Aspose.Words](../../)


