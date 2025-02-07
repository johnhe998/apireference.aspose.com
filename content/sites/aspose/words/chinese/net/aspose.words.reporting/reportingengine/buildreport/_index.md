---
title: ReportingEngine.BuildReport
second_title: Aspose.Words for .NET API 参考
description: ReportingEngine 方法. 使用来自指定源的数据填充指定的模板文档使其成为准备好的报告
type: docs
weight: 40
url: /zh/net/aspose.words.reporting/reportingengine/buildreport/
---
## BuildReport(Document, object) {#buildreport}

使用来自指定源的数据填充指定的模板文档，使其成为准备好的报告。

```csharp
public bool BuildReport(Document document, object dataSource)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| document | Document | 要填充数据的模板文档。 |
| dataSource | Object | 数据源对象。 |

### 返回值

指示模板文档解析是否成功的标志。 返回的标志只有在[`Options`](../options/)属性包括 InlineErrorMessages选项。

### 评论

使用此重载，您可以在模板文档中引用数据源的成员，但不能 引用数据源对象本身。你应该使用`BuildReport` 重载来实现这个。

数据源对象可以是以下类型之一：

* [`XmlDataSource`](../../xmldatasource/)
* [`JsonDataSource`](../../jsondatasource/)
* [`CsvDataSource`](../../csvdatasource/)
* DataSet
* DataTable
* DataRow
* IDataReader
* IDataRecord
* DataView
* DataRowView
* 任何其他任意非动态和非匿名 .NET 类型

有关如何在模板文档中使用不同类型的数据源的信息，请参阅模板语法 参考 (https://docs.aspose.com/display/wordsnet/Template+Syntax)。

### 也可以看看

* class [Document](../../../aspose.words/document/)
* class [ReportingEngine](../)
* 命名空间 [Aspose.Words.Reporting](../../reportingengine/)
* 部件 [Aspose.Words](../../../)

---

## BuildReport(Document, object, string) {#buildreport_1}

使用来自指定源的数据填充指定的模板文档，使其成为准备好的报告。

```csharp
public bool BuildReport(Document document, object dataSource, string dataSourceName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| document | Document | 要填充数据的模板文档。 |
| dataSource | Object | 数据源对象。 |
| dataSourceName | String | 引用模板中数据源对象的名称。 |

### 返回值

指示模板文档解析是否成功的标志。 返回的标志只有在[`Options`](../options/)属性包括 InlineErrorMessages选项。

### 评论

使用此重载，您可以在模板中引用数据源的成员和数据源对象本身。 如果不打算引用数据源对象本身，可以省略*dataSourceName* 传递 null 或使用`BuildReport`过载.

数据源对象可以是以下类型之一：

* [`XmlDataSource`](../../xmldatasource/)
* [`JsonDataSource`](../../jsondatasource/)
* [`CsvDataSource`](../../csvdatasource/)
* DataSet
* DataTable
* DataRow
* IDataReader
* IDataRecord
* DataView
* DataRowView
* 任何其他任意非动态和非匿名 .NET 类型

有关如何在模板文档中使用不同类型的数据源的信息，请参阅模板语法 参考 (https://docs.aspose.com/display/wordsnet/Template+Syntax)。

### 也可以看看

* class [Document](../../../aspose.words/document/)
* class [ReportingEngine](../)
* 命名空间 [Aspose.Words.Reporting](../../reportingengine/)
* 部件 [Aspose.Words](../../../)

---

## BuildReport(Document, object[], string[]) {#buildreport_2}

使用来自指定来源的数据填充指定的模板文档，使其成为准备好的报告。

```csharp
public bool BuildReport(Document document, object[] dataSources, string[] dataSourceNames)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| document | Document | 要填充数据的模板文档。 |
| dataSources | Object[] | 一组数据源对象。 |
| dataSourceNames | String[] | 引用模板中数据源对象的名称数组。 |

### 返回值

指示模板文档解析是否成功的标志。 返回的标志只有在[`Options`](../options/)属性包括 InlineErrorMessages选项。

### 评论

使用此重载，您可以在模板中引用多个数据源对象及其成员。 如果您要 引用数据源的成员而不是数据源对象本身，则可以省略第一个数据源的名称（即为空字符串或null）。其他数据源的名称 必须指定且唯一。

如果要使用单个数据源，请考虑使用`BuildReport` 和`BuildReport`而是重载。

数据源对象可以是以下类型之一：

* [`XmlDataSource`](../../xmldatasource/)
* [`JsonDataSource`](../../jsondatasource/)
* [`CsvDataSource`](../../csvdatasource/)
* DataSet
* DataTable
* DataRow
* IDataReader
* IDataRecord
* DataView
* DataRowView
* 任何其他任意非动态和非匿名 .NET 类型

有关如何在模板文档中使用不同类型的数据源的信息，请参阅模板语法 参考 (https://docs.aspose.com/display/wordsnet/Template+Syntax)。

### 也可以看看

* class [Document](../../../aspose.words/document/)
* class [ReportingEngine](../)
* 命名空间 [Aspose.Words.Reporting](../../reportingengine/)
* 部件 [Aspose.Words](../../../)


