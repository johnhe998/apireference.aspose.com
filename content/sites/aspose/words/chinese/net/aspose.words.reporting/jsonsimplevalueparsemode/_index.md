---
title: Enum JsonSimpleValueParseMode
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Reporting.JsonSimpleValueParseMode 枚举. 指定在加载 JSON 时解析 JSON 简单值null布尔值数字整数和字符串的模式 这种模式不影响日期时间值的解析
type: docs
weight: 4440
url: /zh/net/aspose.words.reporting/jsonsimplevalueparsemode/
---
## JsonSimpleValueParseMode enumeration

指定在加载 JSON 时解析 JSON 简单值（null、布尔值、数字、整数和字符串）的模式。 这种模式不影响日期时间值的解析。

```csharp
public enum JsonSimpleValueParseMode
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Loose | `0` | 指定 JSON 简单值的类型在解析其字符串表示时确定的模式。 例如，JSON 片段 '{ prop: "123" }' 中的 'prop' 类型在此模式下确定为整数。 |
| Strict | `1` | 指定从 JSON 表示法本身确定 JSON 简单值类型的模式。 例如，JSON 片段 '{ prop: "123" }' 中的 'prop' 类型在此模式下确定为字符串。 |

### 也可以看看

* 命名空间 [Aspose.Words.Reporting](../../aspose.words.reporting/)
* 部件 [Aspose.Words](../../)


