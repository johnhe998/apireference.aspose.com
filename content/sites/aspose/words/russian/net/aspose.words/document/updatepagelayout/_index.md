---
title: Document.UpdatePageLayout
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Перестраивает макет страницы документа.
type: docs
weight: 750
url: /ru/net/aspose.words/document/updatepagelayout/
---
## Document.UpdatePageLayout method

Перестраивает макет страницы документа.

```csharp
public void UpdatePageLayout()
```

### Примечания

Этот метод форматирует документ на страницы и обновляет поля, связанные с номерами страниц в документе, такие как PAGE, PAGES, PAGEREF и REF. Актуальная информация о макете страницы требуется для правильного отображения document в форматах с фиксированной страницей.

Этот метод вызывается автоматически при первом преобразовании документа в PDF, XPS, изображение или печать. В этом случае следует позвонить`UpdatePageLayout` рендеринг before снова.

### Примеры

Показывает, когда пересчитывать макет страницы документа.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Сохранение документа в PDF, изображение или печать в первый раз автоматически
// кэшируем макет документа на его страницах.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// Измените документ каким-либо образом.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // В текущей версии Aspose.Words изменение документа не приводит к автоматическому перестроению
// кешированный макет страницы. Если мы хотим кэшированный макет
// чтобы оставаться в курсе, нам нужно будет обновить его вручную.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


