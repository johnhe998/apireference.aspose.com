---
title: FontSourceBase.Type
second_title: Aspose.Words for .NET API 参考
description: FontSourceBase 财产. 返回字体源的类型
type: docs
weight: 20
url: /zh/net/aspose.words.fonts/fontsourcebase/type/
---
## FontSourceBase.Type property

返回字体源的类型。

```csharp
public abstract FontSourceType Type { get; }
```

### 例子

展示如何使用本地文件系统中的字体文件作为字体源。

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### 也可以看看

* enum [FontSourceType](../../fontsourcetype/)
* class [FontSourceBase](../)
* 命名空间 [Aspose.Words.Fonts](../../fontsourcebase/)
* 部件 [Aspose.Words](../../../)


