---
title: Odso.DataSourceType
second_title: Aspose.Words for .NET API Referansı
description: Odso mülk. Bu adres mektup birleştirme için ODSO bağlantı bilgilerinin bir parçası olarak bağlanılacak dış veri kaynağının türünü belirtir. Varsayılan değerDefault .
type: docs
weight: 40
url: /tr/net/aspose.words.settings/odso/datasourcetype/
---
## Odso.DataSourceType property

Bu adres mektup birleştirme için ODSO bağlantı bilgilerinin bir parçası olarak bağlanılacak dış veri kaynağının türünü belirtir. Varsayılan değerDefault .

```csharp
public OdsoDataSourceType DataSourceType { get; set; }
```

### Notlar

Bu ayar, yalnızca bu adres mektup birleştirme için kullanılan veri kaynağı türünün bir önerisidir.

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

* enum [OdsoDataSourceType](../../odsodatasourcetype/)
* class [Odso](../)
* ad alanı [Aspose.Words.Settings](../../odso/)
* toplantı [Aspose.Words](../../../)


