---
title: Enum FontSourceType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fonts.FontSourceType 枚举. 指定字体源的类型
type: docs
weight: 2810
url: /zh/net/aspose.words.fonts/fontsourcetype/
---
## FontSourceType enumeration

指定字体源的类型。

```csharp
public enum FontSourceType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| FontFile | `0` | 一个[`FileFontSource`](../filefontsource/)表示单个字体文件的对象。 |
| FontsFolder | `1` | 一个[`FolderFontSource`](../folderfontsource/)表示带有字体文件的文件夹的对象。 |
| MemoryFont | `2` | 一个[`MemoryFontSource`](../memoryfontsource/)表示内存中单个字体的对象。 |
| SystemFonts | `3` | 一个[`SystemFontSource`](../systemfontsource/)表示安装到系统的所有字体的对象。 |
| FontStream | `4` | 一个[`StreamFontSource`](../streamfontsource/)表示带有字体数据的流的对象。 |

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

* 命名空间 [Aspose.Words.Fonts](../../aspose.words.fonts/)
* 部件 [Aspose.Words](../../)


