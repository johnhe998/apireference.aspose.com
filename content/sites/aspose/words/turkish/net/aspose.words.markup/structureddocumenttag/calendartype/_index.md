---
title: StructuredDocumentTag.CalendarType
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag mülk. Bunun için takvim türünü belirtir SDT . VarsayılanDefault
type: docs
weight: 50
url: /tr/net/aspose.words.markup/structureddocumenttag/calendartype/
---
## StructuredDocumentTag.CalendarType property

Bunun için takvim türünü belirtir **SDT** . VarsayılanDefault

```csharp
public SdtCalendarType CalendarType { get; set; }
```

### Notlar

Bu mülke erişmek yalnızcaDate SDT türü.

Diğer tüm SDT türleri için istisna oluşacaktır.

### Örnekler

Kullanıcıdan yapılandırılmış bir belge etiketiyle bir tarih girmesinin nasıl isteneceğini gösterir.

```csharp
Document doc = new Document();

// Kullanıcıdan bir tarih girmesini isteyen yapılandırılmış bir belge etiketi ekleyin.
// Microsoft Word'de bu öğe "Tarih seçici içerik denetimi" olarak bilinir.
// Microsoft Word'de bu etiketin sağ ucundaki oka tıkladığımızda,
// tıklanabilir bir takvim şeklinde bir açılır pencere göreceğiz.
// Bu açılır pencereyi etiketin göstereceği tarihi seçmek için kullanabiliriz.
StructuredDocumentTag sdtDate = new StructuredDocumentTag(doc, SdtType.Date, MarkupLevel.Inline);

// Tarihi Suudi Arabistan Arapça yerel ayarına göre görüntüleyin.
sdtDate.DateDisplayLocale = CultureInfo.GetCultureInfo("ar-SA").LCID;

// Tarihin görüntüleneceği formatı ayarlayın.
sdtDate.DateDisplayFormat = "dd MMMM, yyyy";
sdtDate.DateStorageFormat = SdtDateStorageFormat.DateTime;

// Hicri takvime göre tarihi göster.
sdtDate.CalendarType = SdtCalendarType.Hijri;

// Kullanıcı Microsoft Word'de bir tarih seçmeden önce, etiket "Bir tarih girmek için burayı tıklayın" metnini görüntüler.
// Etiketin takvimine göre, etiketin varsayılan bir tarih göstermesini sağlamak için "FullDate" özelliğini ayarlayın.
sdtDate.FullDate = new DateTime(1440, 10, 20);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(sdtDate);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Date.docx");
```

### Ayrıca bakınız

* enum [SdtCalendarType](../../sdtcalendartype/)
* class [StructuredDocumentTag](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttag/)
* toplantı [Aspose.Words](../../../)


