---
title: DocumentProperty.ToBool
second_title: Aspose.Words for .NET API 参考
description: DocumentProperty 方法. 将属性值返回为布尔值
type: docs
weight: 60
url: /zh/net/aspose.words.properties/documentproperty/tobool/
---
## DocumentProperty.ToBool method

将属性值返回为布尔值。

```csharp
public bool ToBool()
```

### 评论

如果属性类型不是，则引发异常Boolean.

### 例子

显示自定义文档属性的各种类型转换方法。

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

DateTime authDate = DateTime.Today;
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", authDate);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

Assert.AreEqual(true, properties["Authorized"].ToBool());
Assert.AreEqual("John Doe", properties["Authorized By"].ToString());
Assert.AreEqual(authDate, properties["Authorized Date"].ToDateTime());
Assert.AreEqual(1, properties["Authorized Revision"].ToInt());
Assert.AreEqual(123.45d, properties["Authorized Amount"].ToDouble());
```

### 也可以看看

* class [DocumentProperty](../)
* 命名空间 [Aspose.Words.Properties](../../documentproperty/)
* 部件 [Aspose.Words](../../../)


