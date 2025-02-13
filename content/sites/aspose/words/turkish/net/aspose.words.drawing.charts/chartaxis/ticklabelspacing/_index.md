---
title: ChartAxis.TickLabelSpacing
second_title: Aspose.Words for .NET API Referansı
description: ChartAxis mülk. Onay etiketlerinin çizildiği aralığı alır veya ayarlar.
type: docs
weight: 230
url: /tr/net/aspose.words.drawing.charts/chartaxis/ticklabelspacing/
---
## ChartAxis.TickLabelSpacing property

Onay etiketlerinin çizildiği aralığı alır veya ayarlar.

```csharp
public int TickLabelSpacing { get; set; }
```

### Notlar

Özelliğin metin kategorisi ve seri eksenleri için etkisi vardır. MS Office 2016 yeni çizelgeleri tarafından desteklenmez. Bir değerin geçerli aralığı 1'den büyük veya 1'e eşit.

Bu özelliğin ayarlanması,[`TickLabelSpacingIsAuto`](../ticklabelspacingisauto/) mülk **yanlış**.

### Örnekler

Bir grafik ekseninin onay işaretlerinin ve görüntülenen değerlerinin nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// Y ekseninin küçük onay işaretlerini çizim alanından uzağa işaret edecek şekilde ayarlayın,
// ve ekseni geçmek için ana onay işaretleri.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// Y eksenini, her 10 birimde bir büyük bir onay işareti ve her 1 birimde bir küçük onay işareti gösterecek şekilde ayarlayın.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// Y ekseni sınırlarını -10 ve 20 olarak ayarlayın.
// Bu Y ekseni şimdi 4 ana onay işareti ve 27 küçük onay işareti gösterecektir.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// X ekseni için, ana onay işaretlerini her 10 birimde bir ayarlayın,
// 2.5 birimde her küçük onay işareti.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// Her iki onay işareti türünü de grafik çizim alanı içinde görünecek şekilde yapılandırın.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// X ekseni sınırlarını, X ekseni 5 ana çentik işaretine ve 12 küçük çentik işaretine yayılacak şekilde ayarlayın.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// Değerlerini milyon olarak göstermek için onay etiketlerini ayarlayın.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// Onay etiketlerinin değerlerini göstereceği daha spesifik bir değer ayarlayabiliriz.
// Bu ifade yukarıdakine eşdeğerdir.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### Ayrıca bakınız

* class [ChartAxis](../)
* ad alanı [Aspose.Words.Drawing.Charts](../../chartaxis/)
* toplantı [Aspose.Words](../../../)


