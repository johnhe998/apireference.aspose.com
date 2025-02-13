---
title: Fill.Solid
second_title: Aspose.Words for .NET API Referansı
description: Fill yöntem. Dolguyu tek tip bir renge ayarlar.
type: docs
weight: 200
url: /tr/net/aspose.words.drawing/fill/solid/
---
## Solid() {#solid}

Dolguyu tek tip bir renge ayarlar.

```csharp
public void Solid()
```

### Notlar

Dolgulardan herhangi birini tekrar katı dolguya dönüştürmek için bu yöntemi kullanın.

### Ayrıca bakınız

* class [Fill](../)
* ad alanı [Aspose.Words.Drawing](../../fill/)
* toplantı [Aspose.Words](../../../)

---

## Solid(Color) {#solid_1}

Dolguyu belirtilen tek tip renge ayarlar.

```csharp
public void Solid(Color color)
```

### Notlar

Dolgulardan herhangi birini tekrar katı dolguya dönüştürmek için bu yöntemi kullanın.

### Örnekler

Dolgulardan herhangi birinin katı dolguya nasıl dönüştürüleceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Two color gradient.docx");

// İlk Çalıştırmanın Yazı Tipi için Fill nesnesini alın.
Fill fill = doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.Fill;

// Fontun Dolgu özelliklerini kontrol edin.
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill is transparent at {0}%", fill.Transparency * 100);

// Dolgu tipini tek tip yeşil renkle Düz olarak değiştirin.
fill.Solid(Color.Green);
Console.WriteLine("\nThe fill is changed:");
Console.WriteLine("The type of the fill is: {0}", fill.FillType);
Console.WriteLine("The foreground color of the fill is: {0}", fill.ForeColor);
Console.WriteLine("The fill transparency is {0}%", fill.Transparency * 100);

doc.Save(ArtifactsDir + "Drawing.FillSolid.docx");
```

### Ayrıca bakınız

* class [Fill](../)
* ad alanı [Aspose.Words.Drawing](../../fill/)
* toplantı [Aspose.Words](../../../)


