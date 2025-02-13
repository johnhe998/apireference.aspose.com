---
title: Document.CustomXmlParts
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Получает или задает набор пользовательских частей хранилища данных XML.
type: docs
weight: 80
url: /ru/net/aspose.words/document/customxmlparts/
---
## Document.CustomXmlParts property

Получает или задает набор пользовательских частей хранилища данных XML.

```csharp
public CustomXmlPartCollection CustomXmlParts { get; set; }
```

### Примечания

Aspose.Words загружает и сохраняет пользовательские XML-части только в документах OOXML и DOC.

Это свойство не может быть`нулевой`.

### Примеры

Показывает, как создать тег структурированного документа с пользовательскими данными XML.

```csharp
Document doc = new Document();

// Создайте часть XML, содержащую данные, и добавьте ее в коллекцию документа.
// Если мы включим вкладку «Разработчик» в Microsoft Word,
// мы можем найти элементы из этой коллекции в «Панели сопоставления XML» вместе с несколькими элементами по умолчанию.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello world!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual(Encoding.ASCII.GetBytes(xmlPartContent), xmlPart.Data);
Assert.AreEqual(xmlPartId, xmlPart.Id);

// Ниже приведены два способа обращения к частям XML.
// 1 - По индексу в пользовательской коллекции XML-частей:
Assert.AreEqual(xmlPart, doc.CustomXmlParts[0]);

// 2 - По GUID:
Assert.AreEqual(xmlPart, doc.CustomXmlParts.GetById(xmlPartId));

// Добавляем ассоциацию XML-схемы.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Клонируем часть, а затем вставляем ее в коллекцию.
CustomXmlPart xmlPartClone = xmlPart.Clone();
xmlPartClone.Id = Guid.NewGuid().ToString("B");
doc.CustomXmlParts.Add(xmlPartClone);

Assert.AreEqual(2, doc.CustomXmlParts.Count);

// Перебираем коллекцию и печатаем содержимое каждой части.
using (IEnumerator<CustomXmlPart> enumerator = doc.CustomXmlParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"XML part index {index}, ID: {enumerator.Current.Id}");
        Console.WriteLine($"\tContent: {Encoding.UTF8.GetString(enumerator.Current.Data)}");
        index++;
    }
}

// Используйте метод "RemoveAt", чтобы удалить клонированную часть по индексу.
doc.CustomXmlParts.RemoveAt(1);

Assert.AreEqual(1, doc.CustomXmlParts.Count);

// Клонируем коллекцию частей XML, а затем используем метод «Очистить», чтобы сразу удалить все ее элементы.
CustomXmlPartCollection customXmlParts = doc.CustomXmlParts.Clone();
customXmlParts.Clear();

// Создаем тег структурированного документа, который будет отображать содержимое нашей части, и вставляем его в тело документа.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", string.Empty);

doc.FirstSection.Body.AppendChild(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CustomXml.docx");
```

### Смотрите также

* class [CustomXmlPartCollection](../../../aspose.words.markup/customxmlpartcollection/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


