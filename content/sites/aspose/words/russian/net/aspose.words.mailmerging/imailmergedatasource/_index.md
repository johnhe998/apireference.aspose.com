---
title: Interface IMailMergeDataSource
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.MailMerging.IMailMergeDataSource интерфейс. Реализуйте этот интерфейс чтобы разрешить слияние почты из пользовательского источника данных например списка объектов. Данные MasterDetail также поддерживаются.
type: docs
weight: 3590
url: /ru/net/aspose.words.mailmerging/imailmergedatasource/
---
## IMailMergeDataSource interface

Реализуйте этот интерфейс, чтобы разрешить слияние почты из пользовательского источника данных, например списка объектов. Данные Master-Detail также поддерживаются.

```csharp
public interface IMailMergeDataSource
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [TableName](../../aspose.words.mailmerging/imailmergedatasource/tablename/) { get; } | Возвращает имя источника данных. |

## Методы

| Имя | Описание |
| --- | --- |
| [GetChildDataSource](../../aspose.words.mailmerging/imailmergedatasource/getchilddatasource/)(string) | Механизм слияния Aspose.Words вызывает этот метод, когда обнаруживает начало вложенной области слияния. |
| [GetValue](../../aspose.words.mailmerging/imailmergedatasource/getvalue/)(string, out object) | Возвращает значение для указанного имени поля или false, если поле не найдено. |
| [MoveNext](../../aspose.words.mailmerging/imailmergedatasource/movenext/)() | Переход к следующей записи в источнике данных. |

### Примечания

Когда источник данных создан, он должен быть инициализирован так, чтобы он указывал на BOF (перед первой записью). Механизм слияния почты Aspose.Words будет вызывать[`MoveNext`](./movenext/) чтобы перейти к следующей записи and затем вызвать[`GetValue`](./getvalue/) для каждого поля слияния, которое встречается в документе или в текущей области слияния.

### Примеры

Показывает, как выполнить слияние с источником данных в виде пользовательского объекта.

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

    // Чтобы использовать пользовательский объект в качестве источника данных, он должен реализовать интерфейс IMailMergeDataSource. 
    CustomerMailMergeDataSource dataSource = new CustomerMailMergeDataSource(customers);

    doc.MailMerge.Execute(dataSource);

    doc.Save(ArtifactsDir + "MailMergeCustom.CustomDataSource.docx");
}

/// <summary>
/// Пример класса "объект данных" в вашем приложении.
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
/// Пользовательский источник данных слияния, который вы реализуете, чтобы позволить Aspose.Words 
/// для отправки данных слияния из ваших объектов Customer в документы Microsoft Word.
/// </summary>
public class CustomerMailMergeDataSource : IMailMergeDataSource
{
    public CustomerMailMergeDataSource(List<Customer> customers)
    {
        mCustomers = customers;

        // Когда мы инициализируем источник данных, его позиция должна быть перед первой записью.
        mRecordIndex = -1;
    }

    /// <summary>
    /// Имя источника данных. Используется Aspose.Words только при выполнении слияния почты с повторяемыми областями.
    /// </summary>
    public string TableName
    {
        get { return "Customer"; }
    }

    /// <summary>
    /// Aspose.Words вызывает этот метод, чтобы получить значение для каждого поля данных.
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
                // Возвращаем "false" механизму слияния почты Aspose.Words, чтобы обозначить
                // что мы не смогли найти поле с таким именем.
                fieldValue = null;
                return false;
        }
    }

    /// <summary>
    /// Стандартная реализация перехода к следующей записи в коллекции.
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

### Смотрите также

* пространство имен [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* сборка [Aspose.Words](../../)


