---
title: PdfSaveOptions.OpenHyperlinksInNewWindow
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает значение определяющее будут ли гиперссылки в выходном Pdf document принудительно открываться в новом окне или вкладке браузера.
type: docs
weight: 200
url: /ru/net/aspose.words.saving/pdfsaveoptions/openhyperlinksinnewwindow/
---
## PdfSaveOptions.OpenHyperlinksInNewWindow property

Получает или задает значение, определяющее, будут ли гиперссылки в выходном Pdf document принудительно открываться в новом окне (или вкладке) браузера.

```csharp
public bool OpenHyperlinksInNewWindow { get; set; }
```

### Примечания

Значение по умолчанию:`ЛОЖЬ` . Когда это значение установлено на`истинный` Гиперссылки сохраняются с использованием кода JavaScript. Код JavaScript`app.launchURL("URL", правда);`, где`URL-адрес` является гиперссылкой.

Обратите внимание, что если для этой опции установлено значение`истинный` гиперссылки не работают в некоторых программах для чтения PDF, например Chrome, Firefox.

Действия JavaScript запрещены соответствием PDF/A-1 и PDF/A-2.`ЛОЖЬ` будет использоваться автоматически при сохранении в PDF/A-1 и PDF/A-2.

### Примеры

Показывает, как сохранить гиперссылки в документе, который мы конвертируем в PDF, чтобы они открывали новые страницы при нажатии на них.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertHyperlink("Testlink", @"https://www.google.com/search?q=%20aspose", false);

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "OpenHyperlinksInNewWindow" значение "true", чтобы сохранить все гиперссылки с помощью кода Javascript
// что заставляет читателей открывать эти ссылки в новых окнах/вкладках браузера.
// Установите для свойства OpenHyperlinksInNewWindow значение false, чтобы все гиперссылки сохранялись в обычном режиме.
options.OpenHyperlinksInNewWindow = openHyperlinksInNewWindow;

doc.Save(ArtifactsDir + "PdfSaveOptions.OpenHyperlinksInNewWindow.pdf", options);
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


