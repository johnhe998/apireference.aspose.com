---
title: PclSaveOptions.AddPrinterFont
second_title: Справочник по API Aspose.Words для .NET
description: PclSaveOptions метод. Добавляет информацию о шрифте загруженном производителем на принтер.
type: docs
weight: 50
url: /ru/net/aspose.words.saving/pclsaveoptions/addprinterfont/
---
## PclSaveOptions.AddPrinterFont method

Добавляет информацию о шрифте, загруженном производителем на принтер.

```csharp
public void AddPrinterFont(string fontFullName, string fontPclName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fontFullName | String | Полное название шрифта (например, «Times New Roman Bold Italic»). |
| fontPclName | String | Имя шрифта, используемого в документе Pcl. |

### Примечания

Существует 52 шрифта, которые должны быть встроены в любой принтер в соответствии со спецификацией Pcl. Однако производители могут добавлять в свои устройства некоторые другие шрифты.

### Примеры

Показывает, как заставить принтер заменить все экземпляры определенного шрифта другим шрифтом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Courier";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.AddPrinterFont("Courier New", "Courier");

// При печати этого документа принтер будет использовать шрифт "Courier New"
// для доступа к местам, где в нашем документе использовался шрифт "Courier".
doc.Save(ArtifactsDir + "PclSaveOptions.AddPrinterFont.pcl", saveOptions);
```

### Смотрите также

* class [PclSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pclsaveoptions/)
* сборка [Aspose.Words](../../../)


