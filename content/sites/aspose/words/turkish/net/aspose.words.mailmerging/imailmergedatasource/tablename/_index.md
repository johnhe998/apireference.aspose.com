---
title: IMailMergeDataSource.TableName
second_title: Aspose.Words for .NET API Referansı
description: IMailMergeDataSource mülk. Veri kaynağının adını döndürür.
type: docs
weight: 10
url: /tr/net/aspose.words.mailmerging/imailmergedatasource/tablename/
---
## IMailMergeDataSource.TableName property

Veri kaynağının adını döndürür.

```csharp
public string TableName { get; }
```

### Geri dönüş değeri

Veri kaynağının adı. Veri kaynağının adı yoksa boş dize.

### Notlar

eğer uyguluyorsanız[`IMailMergeDataSource`](../), bu özellikten data kaynağının adını döndürün.

Aspose.Words, şablon belgesinde belirtilen adres mektup birleştirme bölge adıyla eşleşmek için bu adı kullanır. Veri kaynağı adı ve adres mektup birleştirme bölge adı arasındaki karşılaştırma, büyük/küçük harf duyarlı değildir.

### Örnekler

Özel nesne biçimindeki bir veri kaynağıyla adres mektup birleştirmenin nasıl yürütüleceğini gösterir.

```csharp
public void CustomDataSource()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.InsertField(" MERGEFIELD FullName ");
    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD Address ");

    List<Customer> customers = new List<Customer>();
    customers.Add(new Customer("Thomas Hardy", "120 Hanover Sq., London"));
    customers.Add(new Customer("Paolo Accorti", "Via Monte Bianco 34, Torino"));

    // Özel bir nesneyi veri kaynağı olarak kullanmak için IMailMergeDataSource arabirimini uygulaması gerekir. 
    CustomerMailMergeDataSource dataSource = new CustomerMailMergeDataSource(customers);

    doc.MailMerge.Execute(dataSource);

    doc.Save(ArtifactsDir + "MailMergeCustom.CustomDataSource.docx");
}

/// <summary>
/// Uygulamanızda bir "veri varlığı" sınıfı örneği.
/// </summary>
public class Customer
{
    public Customer(string aFullName, string anAddress)
    {
        FullName = aFullName;
        Address = anAddress;
    }

    public string FullName { get; set; }
    public string Address { get; set; }
}

/// <summary>
/// Aspose.Words'e izin vermek için uyguladığınız özel bir adres mektup birleştirme veri kaynağı 
/// Müşteri nesnelerinizden Microsoft Word belgelerine adres mektup birleştirme verileri.
/// </summary>
public class CustomerMailMergeDataSource : IMailMergeDataSource
{
    public CustomerMailMergeDataSource(List<Customer> customers)
    {
        mCustomers = customers;

        // Veri kaynağını başlattığımızda, konumu ilk kayıttan önce olmalıdır.
        mRecordIndex = -1;
    }

    /// <summary>
    /// Veri kaynağının adı. Aspose.Words tarafından yalnızca tekrarlanabilir bölgelerle adres mektup birleştirme yürütülürken kullanılır.
    /// </summary>
    public string TableName
    {
        get { return "Customer"; }
    }

    /// <summary>
    /// Aspose.Words, her veri alanı için bir değer almak için bu yöntemi çağırır.
    /// </summary>
    public bool GetValue(string fieldName, out object fieldValue)
    {
        switch (fieldName)
        {
            case "FullName":
                fieldValue = mCustomers[mRecordIndex].FullName;
                return true;
            case "Address":
                fieldValue = mCustomers[mRecordIndex].Address;
                return true;
            default:
                // Belirtmek için Aspose.Words adres mektup birleştirme motoruna "false" döndür
                // bu isimde bir alan bulamadık.
                fieldValue = null;
                return false;
        }
    }

    /// <summary>
    /// Koleksiyondaki bir sonraki kayda geçmek için standart bir uygulama.
    /// </summary>
    public bool MoveNext()
    {
        if (!IsEof)
            mRecordIndex++;

        return !IsEof;
    }

    public IMailMergeDataSource GetChildDataSource(string tableName)
    {
        return null;
    }

    private bool IsEof
    {
        get { return (mRecordIndex >= mCustomers.Count); }
    }

    private readonly List<Customer> mCustomers;
    private int mRecordIndex;
}
```

### Ayrıca bakınız

* interface [IMailMergeDataSource](../)
* ad alanı [Aspose.Words.MailMerging](../../imailmergedatasource/)
* toplantı [Aspose.Words](../../../)


