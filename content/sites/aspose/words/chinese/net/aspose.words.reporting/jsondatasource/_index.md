---
title: Class JsonDataSource
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Reporting.JsonDataSource 班级. 提供对要在报告中使用的 JSON 文件或流的数据的访问
type: docs
weight: 4430
url: /zh/net/aspose.words.reporting/jsondatasource/
---
## JsonDataSource class

提供对要在报告中使用的 JSON 文件或流的数据的访问。

```csharp
public class JsonDataSource
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [JsonDataSource](jsondatasource/#constructor)(Stream) | 使用解析 JSON 数据的默认选项使用来自 JSON 流的数据创建新数据源。 |
| [JsonDataSource](jsondatasource/#constructor_2)(string) | 使用解析 JSON 数据的默认选项，使用来自 JSON 文件的数据创建新数据源。 |
| [JsonDataSource](jsondatasource/#constructor_1)(Stream, JsonDataLoadOptions) | 使用用于解析 JSON 数据的指定选项，使用来自 JSON 流的数据创建新数据源。 |
| [JsonDataSource](jsondatasource/#constructor_3)(string, JsonDataLoadOptions) | 使用用于解析 JSON 数据的指定选项，使用来自 JSON 文件的数据创建新数据源。 |

### 评论

要在生成报告时访问相应文件或流的数据，请将此类的实例作为 数据源传递给其中一个[`ReportingEngine`](../reportingengine/).BuildReport 重载.

在模板文档中，如果顶级 JSON 元素是一个数组，则`JsonDataSource`实例应该被 对待，就像它是一个DataTable 实例。如果顶级 JSON 元素 是对象，则`JsonDataSource`实例应以与 a相同的方式处理DataRow 实例。有关详细信息，请参阅模板语法参考 (https://docs.aspose.com/display/wordsnet/Template+Syntax)。

在模板文档中，您可以使用 JSON 元素的类型值。为方便起见，引擎将 JSON 简单类型的集合 替换为以下一种：

* Nullable
* Nullable
* Nullable
* Nullable
* String

引擎会根据 JSON 表示形式自动识别额外类型的值。

要覆盖 JSON 数据加载的默认行为，初始化并传递一个[`JsonDataLoadOptions`](../jsondataloadoptions/)instance 到此类的构造函数。

### 也可以看看

* 命名空间 [Aspose.Words.Reporting](../../aspose.words.reporting/)
* 部件 [Aspose.Words](../../)


