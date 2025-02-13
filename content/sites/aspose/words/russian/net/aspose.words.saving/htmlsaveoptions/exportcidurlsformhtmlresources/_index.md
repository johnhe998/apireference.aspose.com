---
title: HtmlSaveOptions.ExportCidUrlsForMhtmlResources
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает следует ли использовать URLадреса CID ContentID для ссылок на ресурсы изображения шрифты CSS включенные в документы MHTML . Значение по умолчаниюЛОЖЬ .
type: docs
weight: 120
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportcidurlsformhtmlresources/
---
## HtmlSaveOptions.ExportCidUrlsForMhtmlResources property

Указывает, следует ли использовать URL-адреса CID (Content-ID) для ссылок на ресурсы (изображения, шрифты, CSS), включенные в документы MHTML . Значение по умолчанию`ЛОЖЬ` .

```csharp
public bool ExportCidUrlsForMhtmlResources { get; set; }
```

### Примечания

Этот параметр влияет только на документы, сохраняемые в формате MHTML.

По умолчанию на ресурсы в документах MHTML ссылаются по имени файла (например, «image.png»), которое сопоставляется с заголовками «Content-Location» частей MIME.

Этот параметр включает альтернативный метод, при котором ссылки на файлы ресурсов записываются как URL-адреса CID (Content-ID) (например, «cid:image.png») и сопоставляются с заголовками «Content-ID».

Теоретически не должно быть никакой разницы между этими двумя методами ссылки, и любой из них должен нормально работать в любом браузере или почтовом агенте. Однако на практике некоторым агентам не удается получить ресурсы по имени файла. Если ваш браузер или почтовый агент отказывается загружать ресурсы, включенные в документ MTHML (не показывает изображения или не загружает стили CSS), попробуйте экспортировать документ с URL-адресами CID.

### Примеры

Показывает, как включить идентификаторы контента для выходных документов MHTML.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Установка этого флага заменит теги «Content-Location»
// с тегами «Content-ID» для каждого ресурса из входного документа.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Mhtml)
{
    ExportCidUrlsForMhtmlResources = exportCidUrlsForMhtmlResources,
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht");

if (exportCidUrlsForMhtmlResources)
{
    Assert.True(outDocContents.Contains("Content-ID: <document.html>"));
    Assert.True(outDocContents.Contains("<link href=3D\"cid:styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('cid:arib=\r\nlk.ttf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"cid:image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
else
{
    Assert.True(outDocContents.Contains("Content-Location: document.html"));
    Assert.True(outDocContents.Contains("<link href=3D\"styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('ariblk.t=\r\ntf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


