---
title: FieldPrintDate.UseLunarCalendar
second_title: Aspose.Words for .NET API Referansı
description: FieldPrintDate mülk. Hicri Ay takviminin mi yoksa İbranice Ay takviminin mi kullanılacağını alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.fields/fieldprintdate/uselunarcalendar/
---
## FieldPrintDate.UseLunarCalendar property

Hicri Ay takviminin mi yoksa İbranice Ay takviminin mi kullanılacağını alır veya ayarlar.

```csharp
public bool UseLunarCalendar { get; set; }
```

### Örnekler

Okunan PRINTDATE alanlarını gösterir.

```csharp
Document doc = new Document(MyDir + "Field sample - PRINTDATE.docx");

// Bir belge bir yazıcı tarafından yazdırıldığında veya PDF olarak yazdırıldığında (ancak PDF'ye aktarılmadığında),
// PRINTDATE alanları, yazdırma işleminin tarihini/saatini görüntüleyecektir.
// Baskı yapılmadıysa, bu alanlar "0/0/0000" gösterecektir.
FieldPrintDate field = (FieldPrintDate)doc.Range.Fields[0];

Assert.AreEqual("3/25/2020 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE ", field.GetFieldCode());

// Aşağıda, PRINTDATE alanına göre üç farklı takvim türü verilmiştir.
// son yazdırma işleminin tarih ve saatini görüntüleyebilir.
// 1 - İslami Ay Takvimi:
field = (FieldPrintDate)doc.Range.Fields[1];

Assert.True(field.UseLunarCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\h", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[2];

// 2 - Ümmü'l-Kura takvimi:
Assert.True(field.UseUmAlQuraCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\u", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[3];

// 3 - Hindistan Ulusal Takvimi:
Assert.True(field.UseSakaEraCalendar);
Assert.AreEqual("1/5/1942 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\s", field.GetFieldCode());
```

### Ayrıca bakınız

* class [FieldPrintDate](../)
* ad alanı [Aspose.Words.Fields](../../fieldprintdate/)
* toplantı [Aspose.Words](../../../)


