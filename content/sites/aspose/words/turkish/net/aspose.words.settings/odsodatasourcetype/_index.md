---
title: Enum OdsoDataSourceType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Settings.OdsoDataSourceType Sıralama. ODSO bağlantı bilgilerinin bir parçası olarak bağlanılacak harici veri kaynağının türünü belirtir.
type: docs
weight: 5590
url: /tr/net/aspose.words.settings/odsodatasourcetype/
---
## OdsoDataSourceType enumeration

ODSO bağlantı bilgilerinin bir parçası olarak bağlanılacak harici veri kaynağının türünü belirtir.

```csharp
public enum OdsoDataSourceType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Text | `0` | Belirli bir belgenin bir metin dosyasına bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeOther. |
| Database | `1` | Belirli bir belgenin bir veritabanına bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeAccess. |
| AddressBook | `2` | Belirli bir belgenin kişilerin adres defterine bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeOAL. |
| Document1 | `3` | Belirli bir belgenin, üreten uygulama tarafından desteklenen başka bir belge biçimine bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeOLEDBWord. |
| Document2 | `4` | Belirli bir belgenin, üreten uygulama tarafından desteklenen başka bir belge biçimine bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeWorks. |
| Native | `5` | Belirli bir belgenin, üreten uygulamaya özgü başka bir belge biçimine bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeOLEDBText |
| Email | `6` | Belirli bir belgenin bir e-posta uygulamasına bağlı olduğunu belirtir. Muhtemelen wdMergeSubTypeOutlook. |
| None | `7` | Harici veri kaynağının türü belirtilmemiş. Muhtemelen wdMergeSubTypeWord. |
| Legacy | `8` | Belirli bir belgenin, üreten uygulama tarafından desteklenen eski bir belge biçimine bağlı olduğunu belirtir Muhtemelen wdMergeSubTypeWord2000. |
| Master | `9` | Belirli bir belgenin, diğer veri kaynaklarını toplayan bir veri kaynağına bağlı olduğunu belirtir. |
| Default | `7` | Şuna eşittir:None . |

### Notlar

OOXML belirtimi bu numaralandırma için çok belirsizdir. Sanırım WdMergeSubType http://msdn.microsoft.com/en-us/library/bb237801.aspx numaralandırmasına karşılık gelebilir.

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

* ad alanı [Aspose.Words.Settings](../../aspose.words.settings/)
* toplantı [Aspose.Words](../../)


