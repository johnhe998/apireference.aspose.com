---
title: IMailMergeDataSource.MoveNext
second_title: Aspose.Words for .NET API 参考
description: IMailMergeDataSource 方法. 前进到数据源中的下一条记录
type: docs
weight: 40
url: /zh/net/aspose.words.mailmerging/imailmergedatasource/movenext/
---
## IMailMergeDataSource.MoveNext method

前进到数据源中的下一条记录。

```csharp
public bool MoveNext()
```

### 返回值

如果成功移动到下一条记录，则为真。如果到达数据源的末尾，则为 False。

### 例子

展示如何使用自定义对象形式的数据源执行邮件合并。

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

    // 要使用自定义对象作为数据源，它必须实现 IMailMergeDataSource 接口。 
    CustomerMailMergeDataSource dataSource = new CustomerMailMergeDataSource(customers);

    doc.MailMerge.Execute(dataSource);

    doc.Save(ArtifactsDir + "MailMergeCustom.CustomDataSource.docx");
}

/// <summary>
/// 应用程序中“数据实体”类的示例。
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
/// 您实现的自定义邮件合并数据源以允许 Aspose.Words 
/// 将您的客户对象中的合并数据邮寄到 Microsoft Word 文档中。
/// </summary>
public class CustomerMailMergeDataSource : IMailMergeDataSource
{
    public CustomerMailMergeDataSource(List<Customer> customers)
    {
        mCustomers = customers;

        // 当我们初始化数据源时，它的位置必须在第一条记录之前。
        mRecordIndex = -1;
    }

    /// <summary>
    /// 数据源的名称。仅在使用可重复区域执行邮件合并时由 Aspose.Words 使用。
    /// </summary>
    public string TableName
    {
        get { return "Customer"; }
    }

    /// <summary>
    /// Aspose.Words 调用此方法来获取每个数据字段的值。
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
                // 向 Aspose.Words 邮件合并引擎返回“false”以表示
                // 我们找不到具有此名称的字段。
                fieldValue = null;
                return false;
        }
    }

    /// <summary>
    /// 移动到集合中的下一条记录的标准实现。
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

### 也可以看看

* interface [IMailMergeDataSource](../)
* 命名空间 [Aspose.Words.MailMerging](../../imailmergedatasource/)
* 部件 [Aspose.Words](../../../)


