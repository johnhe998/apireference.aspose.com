---
title: MemoryFontSource.FontData
second_title: Aspose.Words for .NET API 参考
description: MemoryFontSource 财产. 二进制字体数据
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/memoryfontsource/fontdata/
---
## MemoryFontSource.FontData property

二进制字体数据。

```csharp
public byte[] FontData { get; }
```

### 例子

演示如何将字节数组与字体文件中的数据一起用作字体源。

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### 也可以看看

* class [MemoryFontSource](../)
* 命名空间 [Aspose.Words.Fonts](../../memoryfontsource/)
* 部件 [Aspose.Words](../../../)


