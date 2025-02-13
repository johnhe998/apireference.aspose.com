---
title: FieldAddressBlock.GetFieldNames
second_title: Aspose.Words for .NET API 参考
description: FieldAddressBlock 方法. 返回字段使用的邮件合并字段名称的集合
type: docs
weight: 70
url: /zh/net/aspose.words.fields/fieldaddressblock/getfieldnames/
---
## FieldAddressBlock.GetFieldNames method

返回字段使用的邮件合并字段名称的集合。

```csharp
public string[] GetFieldNames()
```

### 例子

显示如何获取字段使用的邮件合并字段名称。

```csharp
Document doc = new Document(MyDir + "Field sample - ADDRESSBLOCK.docx");

string[] addressFieldsExpect =
{
    "Company", "First Name", "Middle Name", "Last Name", "Suffix", "Address 1", "City", "State",
    "Country or Region", "Postal Code"
};

FieldAddressBlock addressBlockField = (FieldAddressBlock) doc.Range.Fields[0];
string[] addressBlockFieldNames = addressBlockField.GetFieldNames();
```

### 也可以看看

* class [FieldAddressBlock](../)
* 命名空间 [Aspose.Words.Fields](../../fieldaddressblock/)
* 部件 [Aspose.Words](../../../)


