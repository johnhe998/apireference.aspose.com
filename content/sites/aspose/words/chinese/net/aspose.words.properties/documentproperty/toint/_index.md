---
title: DocumentProperty.ToInt
second_title: Aspose.Words for .NET API 参考
description: DocumentProperty 方法. 以整数形式返回属性值
type: docs
weight: 100
url: /zh/net/aspose.words.properties/documentproperty/toint/
---
## DocumentProperty.ToInt method

以整数形式返回属性值。

```csharp
public int ToInt()
```

### 评论

如果属性类型不是则抛出异常Number.

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


