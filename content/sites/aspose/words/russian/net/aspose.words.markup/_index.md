---
title: Aspose.Words.Markup
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Разметка пространство имен содержит классы которые представляют определяемую пользователем семантику в документе смарттеги пользовательский XML и теги структурированного документа элементы управления содержимым.
type: docs
weight: 150
url: /ru/net/aspose.words.markup/
---
**Aspose.Words.Разметка** пространство имен содержит классы, которые представляют определяемую пользователем семантику в документе: смарт-теги, пользовательский XML и теги структурированного документа (элементы управления содержимым).

## Классы

| Учебный класс | Описание |
| --- | --- |
| [CustomPart](./custompart/) | Представляет пользовательскую часть (произвольное содержимое), которая не определена стандартом ISO/IEC 29500. |
| [CustomPartCollection](./custompartcollection/) | Представляет набор[`CustomPart`](../aspose.words.markup/custompart/) объекты. |
| [CustomXmlPart](./customxmlpart/) | Представляет пользовательскую часть хранилища данных XML (пользовательские данные XML в пакете). |
| [CustomXmlPartCollection](./customxmlpartcollection/) | Представляет набор пользовательских XML-частей. Элементы[`CustomXmlPart`](../aspose.words.markup/customxmlpart/) объекты. |
| [CustomXmlProperty](./customxmlproperty/) | Представляет один настраиваемый XML-атрибут или свойство смарт-тега. |
| [CustomXmlPropertyCollection](./customxmlpropertycollection/) | Представляет набор настраиваемых XML-атрибутов или свойств смарт-тегов. |
| [CustomXmlSchemaCollection](./customxmlschemacollection/) | Набор строк, представляющих схемы XML, связанные с пользовательской частью XML. |
| [SdtListItem](./sdtlistitem/) | Этот элемент определяет один элемент списка в родительском элементе.ComboBox или жеDropDownList тег структурированного документа. |
| [SdtListItemCollection](./sdtlistitemcollection/) | Предоставляет доступ к[`SdtListItem`](../aspose.words.markup/sdtlistitem/)элементы тега структурированного документа. |
| [SmartTag](./smarttag/) | Этот элемент указывает наличие смарт-тега вокруг одной или нескольких встроенных структур (прогонов, изображений, полей и т. д.) в абзаце. |
| [StructuredDocumentTag](./structureddocumenttag/) | Представляет тег структурированного документа (SDT или элемент управления содержимым) в документе. |
| [StructuredDocumentTagCollection](./structureddocumenttagcollection/) | Коллекция[`IStructuredDocumentTag`](../aspose.words.markup/istructureddocumenttag/) экземпляры, представляющие теги структурированного документа в указанном диапазоне. |
| [StructuredDocumentTagRangeEnd](./structureddocumenttagrangeend/) | Представляет конец **дальнобойный** тег структурированного документа, который принимает содержимое из нескольких разделов. См. также[`StructuredDocumentTagRangeStart`](../aspose.words.markup/structureddocumenttagrangestart/) узел. |
| [StructuredDocumentTagRangeStart](./structureddocumenttagrangestart/) | Представляет начало **дальнобойный** тег структурированного документа, который принимает содержимое из нескольких разделов. См. также[`StructuredDocumentTagRangeEnd`](../aspose.words.markup/structureddocumenttagrangeend/) . |
| [XmlMapping](./xmlmapping/) | Определяет информацию, которая используется для установления соответствия между тегом структурированного документа parent и элементом XML, хранящимся в пользовательской части данных XML в документе. |
## Интерфейсы

| Интерфейс | Описание |
| --- | --- |
| [IStructuredDocumentTag](./istructureddocumenttag/) | Интерфейс для определения общих данных для[`StructuredDocumentTag`](../aspose.words.markup/structureddocumenttag/) а также[`StructuredDocumentTagRangeStart`](../aspose.words.markup/structureddocumenttagrangestart/) . |
## перечисление

| перечисление | Описание |
| --- | --- |
| [MarkupLevel](./markuplevel/) | Указывает уровень в дереве документов, на котором[`StructuredDocumentTag`](../aspose.words.markup/structureddocumenttag/) может произойти. |
| [SdtAppearance](./sdtappearance/) | Задает внешний вид тега структурированного документа. |
| [SdtCalendarType](./sdtcalendartype/) | Указывает возможные типы календарей, которые можно использовать для указания[`CalendarType`](../aspose.words.markup/structureddocumenttag/calendartype/) в документе Office Open XML. |
| [SdtDateStorageFormat](./sdtdatestorageformat/) | Указывает, как дата для SDT даты сохраняется/извлекается, когда SDT привязан к узлу XML в хранилище данных документа. |
| [SdtType](./sdttype/) | Указывает тип узла тега структурированного документа (SDT). |


