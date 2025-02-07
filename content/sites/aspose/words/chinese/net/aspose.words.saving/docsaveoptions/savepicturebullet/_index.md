---
title: DocSaveOptions.SavePictureBullet
second_title: Aspose.Words for .NET API 参考
description: DocSaveOptions 财产. 什么时候错误的  PictureBullet 数据不保存到输出文档 默认值为 真的.
type: docs
weight: 50
url: /zh/net/aspose.words.saving/docsaveoptions/savepicturebullet/
---
## DocSaveOptions.SavePictureBullet property

什么时候`错误的` , PictureBullet 数据不保存到输出文档。 默认值为 **真的**.

```csharp
public bool SavePictureBullet { get; set; }
```

### 评论

此选项是为 Word 97 提供的，它不能正确处理 PictureBullet 数据。 要删除 PictureBullet 数据，请将选项设置为“false”。

### 例子

显示如何在保存时从文档中省略 PictureBullet 数据。

```csharp
Document doc = new Document(MyDir + "Image bullet points.docx");

// 某些文字处理器，例如 Microsoft Word 97，与 PictureBullet 数据不兼容。
// 通过在 SaveOptions 对象中设置一个标志，
// 我们可以在保存的同时将所有图像要点转换为普通要点。
DocSaveOptions saveOptions = new DocSaveOptions(SaveFormat.Doc);
saveOptions.SavePictureBullet = false;

doc.Save(ArtifactsDir + "DocSaveOptions.PictureBullets.doc", saveOptions);
```

### 也可以看看

* class [DocSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../docsaveoptions/)
* 部件 [Aspose.Words](../../../)


