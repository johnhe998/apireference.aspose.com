---
title: FieldSkipIf.RightExpression
second_title: Aspose.Words for .NET API Referansı
description: FieldSkipIf mülk. Karşılaştırma ifadesinin doğru kısmını alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.fields/fieldskipif/rightexpression/
---
## FieldSkipIf.RightExpression property

Karşılaştırma ifadesinin doğru kısmını alır veya ayarlar.

```csharp
public string RightExpression { get; set; }
```

### Örnekler

SKIPIF alanı kullanılarak adres mektup birleştirmede sayfaların nasıl atlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir SKIPIF alanı ekleyin. Adres mektup birleştirme işleminin geçerli satırı koşulu karşılıyorsa
// bu alanın ifadelerinin belirttiği, ardından adres mektup birleştirme işlemi geçerli satırı iptal eder,
// geçerli birleştirme belgesini atar ve ardından bir sonraki birleştirme belgesini başlatmak için hemen sonraki satıra geçer.
FieldSkipIf fieldSkipIf = (FieldSkipIf) builder.InsertField(FieldType.FieldSkipIf, true);

// Oluşturucuyu SKIPIF alanının ayırıcısına taşıyın, böylece SKIPIF alanına bir MERGEFIELD yerleştirebiliriz.
builder.MoveTo(fieldSkipIf.Separator);
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Department";

// MERGEFIELD, veri tablomuzdaki "Departman" sütununu ifade eder. Eğer o tablodan bir satır
// "Departman" sütununda "HR" değerine sahipse, bu satır koşulu yerine getirecektir.
fieldSkipIf.LeftExpression = "=";
fieldSkipIf.RightExpression = "HR";

// Belgemize içerik ekleyin, veri kaynağını oluşturun ve adres mektup birleştirmeyi yürütün.
builder.MoveToDocumentEnd();
builder.Write("Dear ");
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
builder.Writeln(", ");

 // Bu tablonun üç satırı var ve bunlardan biri SKIPIF alanımızın koşulunu sağlıyor.
// Adres mektup birleştirme iki sayfa üretecek.
DataTable table = new DataTable("Employees");
table.Columns.Add("Name");
table.Columns.Add("Department");
table.Rows.Add("John Doe", "Sales");
table.Rows.Add("Jane Doe", "Accounting");
table.Rows.Add("John Cardholder", "HR");

doc.MailMerge.Execute(table);
doc.Save(ArtifactsDir + "Field.SKIPIF.docx");
```

Adres mektup birleştirmenin çıktı belgelerindeki adres mektup birleştirme kayıtlarını numaralandırmak ve saymak için MERGEREC ve MERGESEQ alanlarının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
builder.Writeln(",");

// Bir MERGEREC alanı, her birleştirme çıktı belgesinde birleştirilen verilerin satır numarasını yazdıracaktır.
builder.Write("\nRow number of record in data source: ");
FieldMergeRec fieldMergeRec = (FieldMergeRec)builder.InsertField(FieldType.FieldMergeRec, true);

Assert.AreEqual(" MERGEREC ", fieldMergeRec.GetFieldCode());

// Bir MERGESEQ alanı, başarılı birleştirmelerin sayısını sayar ve geçerli değeri ilgili her sayfaya yazdırır.
// Adres mektup birleştirme hiçbir satırı atlamaz ve hiçbir SKIP/SKIPIF/NEXT/NEXTIF alanını çağırmazsa, tüm birleştirmeler başarılı olur.
// MERGESEQ ve MERGEREC alanları, adres mektup birleştirmenin başarılı olduğu aynı sonuçları görüntüleyecektir.
builder.Write("\nSuccessful merge number: ");
FieldMergeSeq fieldMergeSeq = (FieldMergeSeq)builder.InsertField(FieldType.FieldMergeSeq, true);

Assert.AreEqual(" MERGESEQ ", fieldMergeSeq.GetFieldCode());

// Adı "John Doe" ise birleştirmeyi atlayacak bir SKIPIF alanı ekleyin.
FieldSkipIf fieldSkipIf = (FieldSkipIf)builder.InsertField(FieldType.FieldSkipIf, true);
builder.MoveTo(fieldSkipIf.Separator);
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
fieldSkipIf.LeftExpression = "=";
fieldSkipIf.RightExpression = "John Doe";

// Bir tanesi "Ad" sütunu için değer olarak "John Doe" olan 3 satırlı bir veri kaynağı oluşturun.
// Bir SKIPIF alanı bu değer tarafından bir kez tetikleneceğinden, adres mektup birleştirmemizin çıktısı 3 yerine 2 sayfa olacaktır.
// 1. sayfada, MERGESEQ ve MERGEREC alanlarının her ikisi de "1" gösterecektir.
// 2. sayfada, MERGEREC alanında "3" ve MERGESEQ alanında "2" görüntülenecektir.
DataTable table = new DataTable("Employees");
table.Columns.Add("Name");
table.Rows.Add(new[] { "Jane Doe" });
table.Rows.Add(new[] { "John Doe" });
table.Rows.Add(new[] { "Joe Bloggs" });

doc.MailMerge.Execute(table);
doc.Save(ArtifactsDir + "Field.MERGEREC.MERGESEQ.docx");
```

### Ayrıca bakınız

* class [FieldSkipIf](../)
* ad alanı [Aspose.Words.Fields](../../fieldskipif/)
* toplantı [Aspose.Words](../../../)


