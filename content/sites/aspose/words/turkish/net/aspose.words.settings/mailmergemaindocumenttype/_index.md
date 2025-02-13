---
title: Enum MailMergeMainDocumentType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Settings.MailMergeMainDocumentType Sıralama. Adres mektup birleştirme kaynak belgesi için olası türleri belirtir.
type: docs
weight: 5540
url: /tr/net/aspose.words.settings/mailmergemaindocumenttype/
---
## MailMergeMainDocumentType enumeration

Adres mektup birleştirme kaynak belgesi için olası türleri belirtir.

```csharp
public enum MailMergeMainDocumentType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| NotAMergeDocument | `0` | Bu belge bir adres mektup birleştirme belgesi değil. |
| FormLetters | `1` | Adres mektup birleştirme kaynak belgesinin mektup türünde olduğunu belirtir. |
| MailingLabels | `2` | Adres mektup birleştirme kaynak belgesinin posta etiketi türünde olduğunu belirtir. |
| Envelopes | `4` | Adres mektup birleştirme kaynak belgesinin zarf türünde olduğunu belirtir. |
| Catalog | `8` | Adres mektup birleştirme kaynak belgesinin katalog türünde olduğunu belirtir. |
| Email | `16` | Adres mektup birleştirme kaynak belgesinin e-posta iletisi türünde olduğunu belirtir. |
| Fax | `32` | Adres mektup birleştirme kaynak belgesinin faks türünde olduğunu belirtir. |
| Default | `0` | Şuna eşittir:NotAMergeDocument |

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

* property [MainDocumentType](../mailmergesettings/maindocumenttype/)
* ad alanı [Aspose.Words.Settings](../../aspose.words.settings/)
* toplantı [Aspose.Words](../../)


