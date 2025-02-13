---
title: Class JsonDataLoadOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Reporting.JsonDataLoadOptions 班级. 表示解析 JSON 数据的选项
type: docs
weight: 4420
url: /zh/net/aspose.words.reporting/jsondataloadoptions/
---
## JsonDataLoadOptions class

表示解析 JSON 数据的选项。

```csharp
public class JsonDataLoadOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [JsonDataLoadOptions](jsondataloadoptions/)() | 使用默认选项初始化此类的新实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AlwaysGenerateRootObject](../../aspose.words.reporting/jsondataloadoptions/alwaysgeneraterootobject/) { get; set; } | 获取或设置一个标志，指示生成的数据源是否将始终包含 JSON root 元素的对象。如果 JSON 根元素包含单个复杂属性，则默认情况下不会创建此类对象。 |
| [ExactDateTimeParseFormats](../../aspose.words.reporting/jsondataloadoptions/exactdatetimeparseformats/) { get; set; } | 获取或设置在加载 JSON 时解析 JSON 日期时间值的确切格式。默认是 **无效的**. |
| [SimpleValueParseMode](../../aspose.words.reporting/jsondataloadoptions/simplevalueparsemode/) { get; set; } | 获取或设置在加载 JSON 时解析 JSON 简单值（空、布尔、数字、整数和字符串） 的模式。这种模式不会影响日期时间值的解析。默认值为 Loose. |

### 评论

可以将此类的实例传递给[`JsonDataSource`](../jsondatasource/).

### 也可以看看

* 命名空间 [Aspose.Words.Reporting](../../aspose.words.reporting/)
* 部件 [Aspose.Words](../../)


