---
title: SaveOptions.UpdateLastSavedTimeProperty
second_title: Aspose.Words for .NET API 参考
description: SaveOptions 财产. 获取或设置一个值确定是否LastSavedTime属性在保存之前更新
type: docs
weight: 190
url: /zh/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/
---
## SaveOptions.UpdateLastSavedTimeProperty property

获取或设置一个值，确定是否[`LastSavedTime`](../../../aspose.words.properties/builtindocumentproperties/lastsavedtime/)属性在保存之前更新。

```csharp
public bool UpdateLastSavedTimeProperty { get; set; }
```

### 例子

显示如何确定在保存时是否保留文档的“上次保存时间”属性。

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
    doc.BuiltInDocumentProperties.LastSavedTime);

// 当我们将文档保存为 OOXML 格式时，我们可以创建一个 OoxmlSaveOptions 对象
// 然后将它传递给文档的保存方法来修改我们如何保存文档。
// 将“UpdateLastSavedTimeProperty”属性设置为“true”以
// 将输出文档的“上次保存时间”内置属性设置为当前日期/时间。
// 将“UpdateLastSavedTimeProperty”属性设置为“false”以
// 保留输入文档的“上次保存时间”内置属性的原始值。
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.UpdateLastSavedTimeProperty = updateLastSavedTimeProperty;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx", saveOptions);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.LastSavedTime.docx");
DateTime lastSavedTimeNew = doc.BuiltInDocumentProperties.LastSavedTime;

if (updateLastSavedTimeProperty)
    Assert.That(DateTime.Now, Is.EqualTo(lastSavedTimeNew).Within(1).Days);
else
    Assert.AreEqual(new DateTime(2021, 5, 11, 6, 32, 0), 
        lastSavedTimeNew);
```

### 也可以看看

* class [SaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../saveoptions/)
* 部件 [Aspose.Words](../../../)


