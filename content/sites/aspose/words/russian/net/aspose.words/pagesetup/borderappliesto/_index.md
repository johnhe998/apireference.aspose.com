---
title: PageSetup.BorderAppliesTo
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Указывает на каких страницах печатается граница страницы.
type: docs
weight: 30
url: /ru/net/aspose.words/pagesetup/borderappliesto/
---
## PageSetup.BorderAppliesTo property

Указывает, на каких страницах печатается граница страницы.

```csharp
public PageBorderAppliesTo BorderAppliesTo { get; set; }
```

### Примеры

Показывает, как создать широкую синюю рамку в верхней части первой страницы.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### Смотрите также

* enum [PageBorderAppliesTo](../../pageborderappliesto/)
* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


