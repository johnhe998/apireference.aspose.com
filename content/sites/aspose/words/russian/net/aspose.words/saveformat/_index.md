---
title: Enum SaveFormat
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.SaveFormat перечисление. Указывает формат в котором сохранен документ.
type: docs
weight: 4580
url: /ru/net/aspose.words/saveformat/
---
## SaveFormat enumeration

Указывает формат, в котором сохранен документ.

```csharp
public enum SaveFormat
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Unknown | `0` | Значение по умолчанию, недопустимое значение для формата файла. |
| Doc | `10` | Сохраняет документ в формате документа Microsoft Word 97 - 2007. |
| Dot | `11` | Сохраняет документ в формате шаблона Microsoft Word 97 - 2007. |
| Docx | `20` | Сохраняет документ как документ Office Open XML WordprocessingML (без макросов). |
| Docm | `21` | Сохраняет документ как документ Office Open XML WordprocessingML с поддержкой макросов. |
| Dotx | `22` | Сохраняет документ как шаблон Office Open XML WordprocessingML (без макросов). |
| Dotm | `23` | Сохраняет документ как шаблон Office Open XML WordprocessingML с поддержкой макросов. |
| FlatOpc | `24` | Сохраняет документ в формате Office Open XML WordprocessingML, хранящемся в простом XML-файле, а не в ZIP-архиве. |
| FlatOpcMacroEnabled | `25` | Сохраняет документ как документ Office Open XML WordprocessingML с поддержкой макросов, хранящийся в простом XML-файле, а не в ZIP-архиве. |
| FlatOpcTemplate | `26` | Сохраняет документ как шаблон Office Open XML WordprocessingML (без макросов), хранящийся в плоском XML-файле, а не в ZIP-архиве. |
| FlatOpcTemplateMacroEnabled | `27` | Сохраняет документ как шаблон Office Open XML WordprocessingML с поддержкой макросов, хранящийся в простом XML-файле, а не в ZIP-архиве. |
| Rtf | `30` | Сохраняет документ в формате RTF. Все символы старше 7 бит экранируются как шестнадцатеричные символы или символы Unicode. |
| WordML | `31` | Сохраняет документ в формате Microsoft Word 2003 WordprocessingML. |
| Pdf | `40` | Сохраняет документ в формате PDF (Adobe Portable Document). |
| Xps | `41` | Сохраняет документ в формате XPS (XML Paper Specification). |
| XamlFixed | `42` | Сохраняет документ в формате Extensible Application Markup Language (XAML) как фиксированный документ. |
| Svg | `44` | Сохраняет документ в формате Svg (масштабируемая векторная графика). |
| HtmlFixed | `45` | Сохраняет документ в формате HTML, используя абсолютно позиционированные элементы |
| OpenXps | `46` | Сохраняет документ в формате OpenXPS (Ecma-388). |
| Ps | `47` | Сохраняет документ в формате PS (PostScript). |
| Pcl | `48` | Сохраняет документ в формате PCL (язык управления принтером). |
| Html | `50` | Сохраняет документ в формате HTML. |
| Mhtml | `51` | Сохраняет документ в формате MHTML (веб-архив). |
| Epub | `52` | Сохраняет документ в формате EPUB. |
| Odt | `60` | Сохраняет документ как текстовый документ ODF. |
| Ott | `61` | Сохраняет документ как шаблон текстового документа ODF. |
| Text | `70` | Сохраняет документ в текстовом формате. |
| XamlFlow | `71` | **Бета.**Сохраняет документ в формате Extensible Application Markup Language (XAML) в виде потокового документа. |
| XamlFlowPack | `72` | **Бета.** Сохраняет документ в формате пакета Extensible Application Markup Language (XAML) в виде потокового документа. |
| Markdown | `73` | Сохраняет документ в формате Markdown. |
| Tiff | `100` | Визуализирует страницу или страницы документа и сохраняет их в одностраничный или многостраничный файл TIFF. |
| Png | `101` | Визуализирует страницу документа и сохраняет ее в виде файла PNG. |
| Bmp | `102` | Визуализирует страницу документа и сохраняет ее как файл BMP. |
| Emf | `103` | Визуализирует страницу документа и сохраняет ее как векторный файл EMF (расширенный метафайл). |
| Jpeg | `104` | Визуализирует страницу документа и сохраняет ее как файл JPEG. |
| Gif | `105` | Визуализирует страницу документа и сохраняет ее как файл GIF. |

### Примеры

Показывает, как конвертировать из формата DOCX в формат HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToHtml.html", SaveFormat.Html);
```

### Смотрите также

* method [Save](../document/save/)
* class [SaveOptions](../../aspose.words.saving/saveoptions/)
* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


