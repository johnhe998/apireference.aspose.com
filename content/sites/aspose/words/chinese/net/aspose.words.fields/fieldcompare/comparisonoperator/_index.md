---
title: FieldCompare.ComparisonOperator
second_title: Aspose.Words for .NET API 参考
description: FieldCompare 财产. 获取或设置比较运算符
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fieldcompare/comparisonoperator/
---
## FieldCompare.ComparisonOperator property

获取或设置比较运算符。

```csharp
public string ComparisonOperator { get; set; }
```

### 例子

显示如何使用 COMPARE 字段比较表达式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldCompare field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "3";
field.ComparisonOperator = "<";
field.RightExpression = "2";
field.Update();

// COMPARE 字段显示“0”或“1”，取决于其陈述的真实性。
// 此语句的结果为假，因此该字段将显示“0”。
Assert.AreEqual(" COMPARE  3 < 2", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

builder.Writeln();

field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "5";
field.ComparisonOperator = "=";
field.RightExpression = "2 + 3";
field.Update();

// 该字段显示“1”，因为该语句为真。
Assert.AreEqual(" COMPARE  5 = \"2 + 3\"", field.GetFieldCode());
Assert.AreEqual("1", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.COMPARE.docx");
```

### 也可以看看

* class [FieldCompare](../)
* 命名空间 [Aspose.Words.Fields](../../fieldcompare/)
* 部件 [Aspose.Words](../../../)


