---
title: PageSetup.FootnoteOptions
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Предоставляет параметры управляющие нумерацией и расположением сносок в этом разделе.
type: docs
weight: 150
url: /ru/net/aspose.words/pagesetup/footnoteoptions/
---
## PageSetup.FootnoteOptions property

Предоставляет параметры, управляющие нумерацией и расположением сносок в этом разделе.

```csharp
public FootnoteOptions FootnoteOptions { get; }
```

### Примеры

Показывает, как настроить параметры, влияющие на сноски/концевые сноски в разделе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// Настройте все сноски в первом разделе, чтобы перезапустить нумерацию с 1
// на каждой новой странице и отображать себя непосредственно под текстом на каждой странице.
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// Настройте все концевые сноски в первом разделе, чтобы вести непрерывный подсчет по всему разделу,
// начиная с 1. Также установите их все так, чтобы они отображались собранными в конце документа.
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### Смотрите также

* class [FootnoteOptions](../../../aspose.words.notes/footnoteoptions/)
* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


