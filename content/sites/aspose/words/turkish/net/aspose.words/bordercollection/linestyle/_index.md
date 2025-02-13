---
title: BorderCollection.LineStyle
second_title: Aspose.Words for .NET API Referansı
description: BorderCollection mülk. Kenarlık stilini alır veya ayarlar.
type: docs
weight: 80
url: /tr/net/aspose.words/bordercollection/linestyle/
---
## BorderCollection.LineStyle property

Kenarlık stilini alır veya ayarlar.

```csharp
public LineStyle LineStyle { get; set; }
```

### Notlar

Koleksiyondaki ilk kenarlığın stilini döndürür.

Çapraz kenarlıklar hariç koleksiyondaki tüm kenarlıkların stilini ayarlar.

### Örnekler

Gölgeli yeşil dalgalı sayfa kenarlığının nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
PageSetup pageSetup = doc.Sections[0].PageSetup;

pageSetup.Borders.LineStyle = LineStyle.DoubleWave;
pageSetup.Borders.LineWidth = 2;
pageSetup.Borders.Color = Color.Green;
pageSetup.Borders.DistanceFromText = 24;
pageSetup.Borders.Shadow = true;

doc.Save(ArtifactsDir + "PageSetup.PageBorders.docx");
```

### Ayrıca bakınız

* enum [LineStyle](../../linestyle/)
* class [BorderCollection](../)
* ad alanı [Aspose.Words](../../bordercollection/)
* toplantı [Aspose.Words](../../../)


