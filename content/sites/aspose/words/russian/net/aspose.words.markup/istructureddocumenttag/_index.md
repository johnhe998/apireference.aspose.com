---
title: Interface IStructuredDocumentTag
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Markup.IStructuredDocumentTag интерфейс. Интерфейс для определения общих данных дляStructuredDocumentTag а такжеStructuredDocumentTagRangeStart .
type: docs
weight: 3730
url: /ru/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

Интерфейс для определения общих данных для[`StructuredDocumentTag`](../structureddocumenttag/) а также[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/) .

```csharp
public interface IStructuredDocumentTag
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | Получает или задает цвет тега структурированного документа. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | Указывает уникальный постоянный числовой идентификатор только для чтения для этого **СДТ**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | Указывает, будет ли содержимое этого **СДТ** должен интерпретироваться как содержащий заполнитель text (в отличие от обычного текстового содержимого в SDT). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | Получает уровень, на котором **СДТ** встречается в дереве документа. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | Если установлено значение true, это свойство запрещает пользователю удалять это **СДТ** . |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | Если установлено значение true, это свойство запрещает пользователю редактировать содержимое этого **СДТ** . |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | Получает[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) содержащий текст-заполнитель, который должен отображаться, когда содержимое этого запуска SDT пусто, связанный сопоставленный XML-элемент пуст, как указано через[`XmlMapping`](./xmlmapping/) element или[`IsShowingPlaceholderText`](./isshowingplaceholdertext/) элемент истинный. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | Получает или задает имя[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) содержащий текст-заполнитель. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | Получает тип этого **Тег структурированного документа** . |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | Указывает тег, связанный с текущим узлом SDT. Не может быть нулевым. |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | Указывает понятное имя, связанное с этим **СДТ** . Не может быть нулевым. |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | Получает строку, представляющую XML, содержащийся в узле вFlatOpc формат. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | Получает объект, представляющий сопоставление этого тега структурированного документа с XML data в пользовательской XML-части текущего документа. |

## Методы

| Имя | Описание |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | Возвращает значение true, если этот экземпляр является ранжированным тегом структурированного документа. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | Возвращает объект узла, который реализует этот интерфейс. |

### Смотрите также

* пространство имен [Aspose.Words.Markup](../../aspose.words.markup/)
* сборка [Aspose.Words](../../)


