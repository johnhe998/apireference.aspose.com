---
title: RevisionOptions.InsertedTextEffect
second_title: Aspose.Words for .NET API Referansı
description: RevisionOptions mülk. Eklenen içeriğe uygulanacak efekti belirlemeye izin verirInsertion . Varsayılan değerUnderline .
type: docs
weight: 50
url: /tr/net/aspose.words.layout/revisionoptions/insertedtexteffect/
---
## RevisionOptions.InsertedTextEffect property

Eklenen içeriğe uygulanacak efekti belirlemeye izin verirInsertion . Varsayılan değerUnderline .

```csharp
public RevisionTextEffect InsertedTextEffect { get; set; }
```

### Notlar

DeğerleriHidden veDoubleStrikeThrough izin verilmez ve neden olurArgumentOutOfRangeException.

### Örnekler

Düzeltmelerin görünümünün nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Revizyonların görünümünü kontrol eden RevisionOptions nesnesini alın.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Ekleme revizyonlarını yeşil ve italik olarak işle.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Silme revizyonlarını kırmızı ve kalın olarak işle.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Aynı metin bir hareket revizyonunda iki kez görünecek:
// bir kez kalkış noktasında ve bir kez varış noktasında.
// Taşınan revizyondaki metni çift vuruşla sarıya çevir
// ve taşınan revizyonda altı çift mavi çizgili.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Format revizyonlarını koyu kırmızı ve kalın olarak işleyin.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Sayfanın sol tarafında, revizyonlardan etkilenen satırların yanına kalın bir lacivert çubuk yerleştirin.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Revizyon işaretlerini ve orijinal metni göster.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Yeşil balonlarda görünecek hareket, silme, biçimlendirme revizyonları ve yorumları alın
// sayfanın sağ tarafında.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Bu özellikler yalnızca .pdf veya .jpg gibi biçimler için geçerlidir.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Ayrıca bakınız

* enum [RevisionTextEffect](../../revisiontexteffect/)
* class [RevisionOptions](../)
* ad alanı [Aspose.Words.Layout](../../revisionoptions/)
* toplantı [Aspose.Words](../../../)


