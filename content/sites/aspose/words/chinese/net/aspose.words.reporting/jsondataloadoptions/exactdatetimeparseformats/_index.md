---
title: JsonDataLoadOptions.ExactDateTimeParseFormats
second_title: Aspose.Words for .NET API 参考
description: JsonDataLoadOptions 财产. 获取或设置在加载 JSON 时解析 JSON 日期时间值的确切格式默认是 无效的.
type: docs
weight: 30
url: /zh/net/aspose.words.reporting/jsondataloadoptions/exactdatetimeparseformats/
---
## JsonDataLoadOptions.ExactDateTimeParseFormats property

获取或设置在加载 JSON 时解析 JSON 日期时间值的确切格式。默认是 **无效的**.

```csharp
public IEnumerable<string> ExactDateTimeParseFormats { get; set; }
```

### 评论

使用 Microsoft® JSON 日期时间格式编码的字符串（例如，“/Date(1224043200000)/”）始终被 识别为日期时间值，无论此属性的值如何。该属性定义了在以下列方式从字符串中解析日期时间值时要使用的其他 格式：

* 什么时候`ExactDateTimeParseFormats`是 **无效的** , ISO-8601 格式和当前、美国英语和新西兰英语文化支持的所有日期时间格式 在 提到的顺序中额外使用。
* 什么时候`ExactDateTimeParseFormats`包含字符串，它们用作利用当前区域性的附加 date-time 格式。
* 什么时候`ExactDateTimeParseFormats`为空，不使用其他日期时间格式。

### 也可以看看

* class [JsonDataLoadOptions](../)
* 命名空间 [Aspose.Words.Reporting](../../jsondataloadoptions/)
* 部件 [Aspose.Words](../../../)


