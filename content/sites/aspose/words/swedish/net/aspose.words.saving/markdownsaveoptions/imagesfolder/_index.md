---
title: MarkdownSaveOptions.ImagesFolder
second_title: Aspose.Words för .NET API Referens
description: MarkdownSaveOptions fast egendom. Anger den fysiska mappen där bilderna sparas när ett dokument exporteras till Markdown formatera. Standard är en tom sträng.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

Anger den fysiska mappen där bilderna sparas när ett dokument exporteras till Markdown formatera. Standard är en tom sträng.

```csharp
public string ImagesFolder { get; set; }
```

### Anmärkningar

När du sparar en[`Document`](../../../aspose.words/document/) iMarkdown format, Aspose.Words måste spara alla bilder som är inbäddade i dokumentet som fristående filer. `ImagesFolder` låter dig ange var bilderna ska sparas.

Om du sparar ett dokument i en fil och anger ett filnamn, sparar Aspose.Words, som standard, bilderna i samma mapp där dokumentfilen sparas. Använda sig av`ImagesFolder` för att åsidosätta detta beteende.

Om du sparar ett dokument i en ström, har Aspose.Words ingen folder där bilderna ska sparas, men måste fortfarande spara bilderna någonstans. I det här fallet, måste du ange en tillgänglig mapp i`ImagesFolder` egenskap.

Om mappen som anges av`ImagesFolder` inte finns skapas den automatiskt.

### Se även

* class [MarkdownSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../markdownsaveoptions/)
* hopsättning [Aspose.Words](../../../)


