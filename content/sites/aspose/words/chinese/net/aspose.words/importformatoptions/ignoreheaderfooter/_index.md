---
title: ImportFormatOptions.IgnoreHeaderFooter
second_title: Aspose.Words for .NET API 参考
description: ImportFormatOptions 财产. 获取或设置一个布尔值该值指定忽略页眉/页脚内容的源格式 ifKeepSourceFormatting使用模式 默认值为真的.
type: docs
weight: 30
url: /zh/net/aspose.words/importformatoptions/ignoreheaderfooter/
---
## ImportFormatOptions.IgnoreHeaderFooter property

获取或设置一个布尔值，该值指定忽略页眉/页脚内容的源格式 ifKeepSourceFormatting使用模式。 默认值为`真的`.

```csharp
public bool IgnoreHeaderFooter { get; set; }
```

### 例子

显示如何指定忽略或不指定页眉/页脚内容的源格式。

```csharp
Document dstDoc = new Document(MyDir + "Document.docx");
Document srcDoc = new Document(MyDir + "Header and footer types.docx");

ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.IgnoreHeaderFooter = false;

dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.DoNotIgnoreHeaderFooter.docx");
```

### 也可以看看

* class [ImportFormatOptions](../)
* 命名空间 [Aspose.Words](../../importformatoptions/)
* 部件 [Aspose.Words](../../../)


