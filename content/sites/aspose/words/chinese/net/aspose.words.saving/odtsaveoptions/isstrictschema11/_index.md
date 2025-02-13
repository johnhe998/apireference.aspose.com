---
title: OdtSaveOptions.IsStrictSchema11
second_title: Aspose.Words for .NET API 参考
description: OdtSaveOptions 财产. 指定导出是否应严格符合 ODT 规范 1.1 OOo 3.0 在文件包含 ODT 1.2 的元素和属性时正确显示文件 使用false表示此目的或true表示严格符合规范 1.1. 默认值为 错误的.
type: docs
weight: 20
url: /zh/net/aspose.words.saving/odtsaveoptions/isstrictschema11/
---
## OdtSaveOptions.IsStrictSchema11 property

指定导出是否应严格符合 ODT 规范 1.1。 OOo 3.0 在文件包含 ODT 1.2 的元素和属性时正确显示文件。 使用“false”表示此目的，或“true”表示严格符合规范 1.1. 默认值为 **错误的**.

```csharp
public bool IsStrictSchema11 { get; set; }
```

### 例子

展示如何使保存的文档符合旧的 ODT 模式。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### 也可以看看

* class [OdtSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../odtsaveoptions/)
* 部件 [Aspose.Words](../../../)


