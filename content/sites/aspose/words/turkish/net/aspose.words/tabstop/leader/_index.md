---
title: TabStop.Leader
second_title: Aspose.Words for .NET API Referansı
description: TabStop mülk. Sekme karakteri altında görüntülenen öncü çizginin türünü alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words/tabstop/leader/
---
## TabStop.Leader property

Sekme karakteri altında görüntülenen öncü çizginin türünü alır veya ayarlar.

```csharp
public TabLeader Leader { get; set; }
```

### Örnekler

TOC ile ilgili paragraflarda sağ sekme durağının konumunun nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// İçindekiler sonuç tabanlı stiller ile tüm paragrafları yineleyin; Bu, TOC ve TOC9 arasındaki herhangi bir stildir.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Bu paragrafta kullanılan ilk sekmeyi alın, bu, sayfa numaralarını hizalamak için kullanılan sekme olmalıdır.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // İlk varsayılan sekmeyi değiştirin, özel bir sekme durağı ile durdurun.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Ayrıca bakınız

* enum [TabLeader](../../tableader/)
* class [TabStop](../)
* ad alanı [Aspose.Words](../../tabstop/)
* toplantı [Aspose.Words](../../../)


