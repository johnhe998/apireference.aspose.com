---
title: MailMergeSettings.ViewMergedData
second_title: Aspose.Words for .NET API Referansı
description: MailMergeSettings mülk. Microsoft Wordün birleştirme alanlarının eklendiği belirtilen harici veri kaynağından gelen verileri görüntüleyeceğini belirtir örneğin birleştirilmiş verileri önizleme. Varsayılan değeryanlış .
type: docs
weight: 170
url: /tr/net/aspose.words.settings/mailmergesettings/viewmergeddata/
---
## MailMergeSettings.ViewMergedData property

Microsoft Word'ün, birleştirme alanlarının eklendiği belirtilen harici veri kaynağından gelen verileri görüntüleyeceğini belirtir (örneğin, birleştirilmiş verileri önizleme). Varsayılan değer`yanlış` .

```csharp
public bool ViewMergedData { get; set; }
```

### Örnekler

Office Veri Kaynağı Nesnesindeki verilerle adres mektup birleştirmenin nasıl yürütüleceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// "|" ile ASCII dosyası biçiminde bir veri kaynağı oluşturun karakter
// sütunları ayıran sınırlayıcı görevi görür. İlk satır, üç sütunun adını içerir,
// ve sonraki her satır, kendi değerlerine sahip bir satırdır.
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// Bu belgeyi Microsoft Word'de açmak, içeriği görüntülemeden önce adres mektup birleştirmeyi yürütecektir. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Ayrıca bakınız

* class [MailMergeSettings](../)
* ad alanı [Aspose.Words.Settings](../../mailmergesettings/)
* toplantı [Aspose.Words](../../../)


