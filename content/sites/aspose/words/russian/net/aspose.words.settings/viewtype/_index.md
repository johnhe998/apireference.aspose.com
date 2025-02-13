---
title: Enum ViewType
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Settings.ViewType перечисление. Возможные значения режима просмотра в Microsoft Word.
type: docs
weight: 5660
url: /ru/net/aspose.words.settings/viewtype/
---
## ViewType enumeration

Возможные значения режима просмотра в Microsoft Word.

```csharp
public enum ViewType
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Документ должен отображаться в представлении приложения по умолчанию. |
| Reading | `0` | Документ должен отображаться в представлении приложения по умолчанию. |
| PageLayout | `1` | Документ должен быть открыт в представлении, отображающем документ в том виде, в котором он будет напечатан. |
| Outline | `3` | Документ должен быть представлен в виде, оптимизированном для обрисовки или создания длинных документов. |
| Normal | `4` | Документ должен быть представлен в виде, оптимизированном для обрисовки или создания длинных документов. |
| Web | `5` | Документ должен отображаться в представлении, имитирующем способ отображения этого документа на веб-странице. |

### Примеры

Показывает, как установить пользовательский коэффициент масштабирования, который старые версии Microsoft Word будут применять к документу при загрузке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

### Смотрите также

* class [ViewOptions](../viewoptions/)
* property [ViewType](../viewoptions/viewtype/)
* пространство имен [Aspose.Words.Settings](../../aspose.words.settings/)
* сборка [Aspose.Words](../../)


