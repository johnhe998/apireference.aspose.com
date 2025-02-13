---
title: SaveOptions.CreateSaveOptions
second_title: Aspose.Words for .NET API 参考
description: SaveOptions 方法. 创建适合指定保存格式的类的保存选项对象
type: docs
weight: 10
url: /zh/net/aspose.words.saving/saveoptions/createsaveoptions/
---
## CreateSaveOptions(SaveFormat) {#createsaveoptions}

创建适合指定保存格式的类的保存选项对象。

```csharp
public static SaveOptions CreateSaveOptions(SaveFormat saveFormat)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| saveFormat | SaveFormat | 要为其创建保存选项对象的保存格式。 |

### 返回值

派生自的类的对象[`SaveOptions`](../).

### 例子

显示在将大型文档呈现为 PDF 时优化内存消耗的选项。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// 将“MemoryOptimization”属性设置为“true”以降低大型文档保存操作的内存占用
// 以增加操作的持续时间为代价。
// 将“MemoryOptimization”属性设置为“false”以正常将文档保存为PDF。
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### 也可以看看

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [SaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../saveoptions/)
* 部件 [Aspose.Words](../../../)

---

## CreateSaveOptions(string) {#createsaveoptions_1}

创建适合给定文件名中指定的文件扩展名的类的保存选项对象。

```csharp
public static SaveOptions CreateSaveOptions(string fileName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| fileName | String | 此文件名的扩展名确定要创建的保存选项对象的类。 |

### 返回值

派生自的类的对象[`SaveOptions`](../).

### 例子

显示如何为没有附加模板的文档设置默认模板。

```csharp
Document doc = new Document();

// 启用自动样式更新，但不附加模板文档。
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// 由于没有模板文档，因此文档无处跟踪样式更改。
// 使用 SaveOptions 对象自动设置模板
// 如果我们正在保存的文档没有。
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### 也可以看看

* class [SaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../saveoptions/)
* 部件 [Aspose.Words](../../../)


