---
title: FieldAddressBlock.IncludeCountryOrRegionName
second_title: Aspose.Words for .NET API 参考
description: FieldAddressBlock 财产. 获取或设置是否包含国家/地区名称
type: docs
weight: 40
url: /zh/net/aspose.words.fields/fieldaddressblock/includecountryorregionname/
---
## FieldAddressBlock.IncludeCountryOrRegionName property

获取或设置是否包含国家/地区名称。

```csharp
public string IncludeCountryOrRegionName { get; set; }
```

### 例子

显示如何插入 ADDRESSBLOCK 字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, true);

Assert.AreEqual(" ADDRESSBLOCK ", field.GetFieldCode());

// 将此设置为“2”将包括所有国家和地区，
// 除非它是 ExcludedCountryOrRegionName 属性中指定的那个。
field.IncludeCountryOrRegionName = "2";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "United States";
field.NameAndAddressFormat = "<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>";

// 默认情况下，此属性将包含文档第一个字符的语言 ID。
// 我们可以为字段设置不同的文化来格式化结果，如下所示。
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(
    " ADDRESSBLOCK  \\c 2 \\d \\e \"United States\" \\f \"<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>\" \\l 1033",
    field.GetFieldCode());
```

### 也可以看看

* class [FieldAddressBlock](../)
* 命名空间 [Aspose.Words.Fields](../../fieldaddressblock/)
* 部件 [Aspose.Words](../../../)


