---
title: StructuredDocumentTag.Placeholder
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. ПолучаетBuildingBlock содержащий текстзаполнитель который должен отображаться когда содержимое этого запуска SDT пусто связанный сопоставленный XMLэлемент пуст как указано черезXmlMapping element илиIsShowingPlaceholderText элемент истинный.
type: docs
weight: 230
url: /ru/net/aspose.words.markup/structureddocumenttag/placeholder/
---
## StructuredDocumentTag.Placeholder property

Получает[`BuildingBlock`](../../../aspose.words.buildingblocks/buildingblock/) содержащий текст-заполнитель, который должен отображаться, когда содержимое этого запуска SDT пусто, связанный сопоставленный XML-элемент пуст, как указано через[`XmlMapping`](../xmlmapping/) element или[`IsShowingPlaceholderText`](../isshowingplaceholdertext/) элемент истинный.

```csharp
public BuildingBlock Placeholder { get; }
```

### Примечания

Может быть нулевым, что означает, что заполнитель неприменим для этого Sdt.

### Примеры

Показывает, как использовать содержимое стандартного блока в качестве настраиваемого текста-заполнителя для тега структурированного документа.

```csharp
Document doc = new Document();

// Вставьте структурированный текстовый тег документа типа "Обычный текст", который будет функционировать как текстовое поле.
// Содержимое, которое будет отображаться по умолчанию, — это «Нажмите здесь, чтобы ввести текст». быстрый.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Мы можем заставить тег отображать содержимое стандартного блока вместо текста по умолчанию.
// Сначала добавьте в глоссарий стандартный блок с содержимым.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;

BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "Custom Placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.AppendChild(new Body(glossaryDoc));
substituteBlock.FirstSection.Body.AppendParagraph("Custom placeholder text.");

glossaryDoc.AppendChild(substituteBlock);

// Затем используйте свойство «PlaceholderName» тега структурированного документа, чтобы сослаться на этот стандартный блок по имени.
tag.PlaceholderName = "Custom Placeholder";

// Если «PlaceholderName» относится к существующему блоку в документе глоссария родительского документа,
// мы сможем проверить строительный блок с помощью свойства «Placeholder».
Assert.AreEqual(substituteBlock, tag.Placeholder);

// Установите для свойства "IsShowingPlaceholderText" значение "true", чтобы обрабатывать
// текущее содержимое тега структурированного документа в качестве текста-заполнителя.
// Это означает, что при нажатии на текстовое поле в Microsoft Word сразу будет выделено все содержимое тега.
// Установите для свойства "IsShowingPlaceholderText" значение "false", чтобы получить
// структурированный тег документа для обработки его содержимого как текста, уже введенного пользователем.
// Щелчок по этому тексту в Microsoft Word поместит мигающий курсор в место щелчка.
tag.IsShowingPlaceholderText = isShowingPlaceholderText;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlaceholderBuildingBlock.docx");
```

### Смотрите также

* class [BuildingBlock](../../../aspose.words.buildingblocks/buildingblock/)
* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


