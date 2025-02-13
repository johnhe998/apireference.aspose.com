---
title: MailMerge.ExecuteADO
second_title: Aspose.Words for .NET API Referansı
description: MailMerge yöntem. Bir ADO Recordset nesnesinden belgeye adres mektup birleştirme gerçekleştirir.
type: docs
weight: 190
url: /tr/net/aspose.words.mailmerging/mailmerge/executeado/
---
## MailMerge.ExecuteADO method

Bir ADO Recordset nesnesinden belgeye adres mektup birleştirme gerçekleştirir.

```csharp
public void ExecuteADO(object recordset)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| recordset | Object | ADO Kayıt Kümesi veya Kayıt nesnesi. |

### Notlar

Bu yöntem, ASP veya Visual Basic 6.0 kullanılarak oluşturulmuş bir uygulama gibi yönetilmeyen koddan Aspose.Words sınıflarını as COM nesneleri kullanmayı düşündüğünüzde kullanışlıdır.

Bu yöntem yok sayarRemoveUnusedRegions seçenek.

Daha fazla bilgi için MailMerge.Execute(DataTable) açıklamasına bakın.

### Örnekler

```csharp
[VBScript]

Dim RS
Set RS = CreateObject("ADODB.Recordset")
RS.Open _
    "SELECT TOP 50 * FROM Customers ORDER BY Country, CompanyName", _
    "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb"

Dim License
Set License = CreateObject("Aspose.Words.License")
License.SetLicense "C:\MyPath\MyLicense.lic"

Dim Helper
Set Helper = CreateObject("Aspose.Words.ComHelper")
Dim Doc
Set Doc = Helper.Open("CustomerLabels.doc")

Doc.MailMerge.ExecuteADO RS
Doc.Save "C:\MyPath\CustomerLabels Out VBScript.doc"
```

Bir ADO veri kümesindeki verilerle adres mektup birleştirmenin nasıl çalıştırılacağını gösterir.

```csharp
public void ExecuteADO()
{
    Document doc = CreateSourceDocADOMailMerge();

    // ADO DataSets ile çalışmak için Microsoft ActiveX Data Objects kitaplığına bir referans eklememiz gerekecek,
    // .NET dağıtımına dahil olan ve "adodb.dll" içinde depolanan.
    ADODB.Connection connection = new ADODB.Connection();

    // "Northwind" veritabanı dosyasına işaret eden bir bağlantı dizesi oluşturun
    // yerel dosya sistemimizde ve bir bağlantı açın.
    string connectionString = @"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + DatabaseDir + "Northwind.mdb";
    connection.Open(connectionString);

    // Veritabanımızda bir SQL komutu çalıştırarak DataSet'imizi doldurun.
    // Sonuç tablosundaki sütunların adlarının karşılık gelmesi gerekecek
    // verilerimizi barındıracak MERGEFIELDS değerlerine.
    const string command = @"SELECT ProductName, QuantityPerUnit, UnitPrice FROM Products";

    ADODB.Recordset recordset = new ADODB.Recordset();
    recordset.Open(command, connection);

    // Adres mektup birleştirmeyi yürütün ve belgeyi kaydedin.
    doc.MailMerge.ExecuteADO(recordset);
    doc.Save(ArtifactsDir + "MailMerge.ExecuteADO.docx");
}

/// <summary>
/// Boş bir belge oluşturun ve onu adres mektup birleştirme yürütüldüğünde verileri kabul edecek MERGEFIELDS ile doldurun.
/// </summary>
private static Document CreateSourceDocADOMailMerge()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Product:\t");
    builder.InsertField(" MERGEFIELD ProductName");
    builder.Writeln();
    builder.InsertField(" MERGEFIELD QuantityPerUnit");
    builder.Write(" for $");
    builder.InsertField(" MERGEFIELD UnitPrice");

    return doc;
}
```

### Ayrıca bakınız

* class [MailMerge](../)
* ad alanı [Aspose.Words.MailMerging](../../mailmerge/)
* toplantı [Aspose.Words](../../../)


