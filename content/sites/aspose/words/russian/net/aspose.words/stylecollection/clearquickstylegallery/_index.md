---
title: StyleCollection.ClearQuickStyleGallery
second_title: Справочник по API Aspose.Words для .NET
description: StyleCollection метод. Удаляет все стили из панели галереи быстрых стилей.
type: docs
weight: 80
url: /ru/net/aspose.words/stylecollection/clearquickstylegallery/
---
## StyleCollection.ClearQuickStyleGallery method

Удаляет все стили из панели галереи быстрых стилей.

```csharp
public void ClearQuickStyleGallery()
```

### Примеры

Показывает, как удалять стили с панели «Галерея стилей».

```csharp
Document doc = new Document();

// Обратите внимание, что удаление стилей пока работает только с форматом DOCX.
doc.Styles.ClearQuickStyleGallery();

doc.Save(ArtifactsDir + "Styles.RemoveStylesFromStyleGallery.docx");
```

### Смотрите также

* class [StyleCollection](../)
* пространство имен [Aspose.Words](../../stylecollection/)
* сборка [Aspose.Words](../../../)


