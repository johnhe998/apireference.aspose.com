---
title: Class FontSubstitutionSettings
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fonts.FontSubstitutionSettings 班级. 指定字体替换机制设置
type: docs
weight: 2830
url: /zh/net/aspose.words.fonts/fontsubstitutionsettings/
---
## FontSubstitutionSettings class

指定字体替换机制设置。

```csharp
public class FontSubstitutionSettings
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DefaultFontSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/defaultfontsubstitution/) { get; } | 与默认字体替换规则相关的设置。 |
| [FontConfigSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontconfigsubstitution/) { get; } | 与字体配置替换规则相关的设置。 |
| [FontInfoSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontinfosubstitution/) { get; } | 字体信息替换规则相关设置。 |
| [FontNameSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/fontnamesubstitution/) { get; } | 与字体名称替换规则相关的设置。 |
| [TableSubstitution](../../aspose.words.fonts/fontsubstitutionsettings/tablesubstitution/) { get; } | 与表替换规则相关的设置。 |

### 评论

字体替换过程由几个规则组成，这些规则按特定顺序逐个检查。 如果第一个规则无法解析字体，则检查第二个规则，依此类推。

规则顺序如下： 1. 字体名称替换规则（默认开启） 2. 字体配置替换规则（默认关闭） 3. 表格替换规则（默认开启） 4. 字体信息替换规则(默认开启) 5. 默认字体规则(默认开启)

请注意，字体信息替换规则将始终解析字体，如果[`FontInfo`](../fontinfo/)is available 并将覆盖默认字体规则。如果要使用默认字体规则，则应禁用 字体信息替换规则。

请注意，字体配置替换规则将在大多数情况下解析字体，因此会覆盖所有其他规则。

### 例子

显示如何访问文档的系统字体源和设置字体替换。

```csharp
Document doc = new Document();
doc.FontSettings = new FontSettings();

// 默认情况下，空白文档始终包含系统字体源。
Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);

SystemFontSource systemFontSource = (SystemFontSource) doc.FontSettings.GetFontsSources()[0];
Assert.AreEqual(FontSourceType.SystemFonts, systemFontSource.Type);
Assert.AreEqual(0, systemFontSource.Priority);

PlatformID pid = Environment.OSVersion.Platform;
bool isWindows = (pid == PlatformID.Win32NT) || (pid == PlatformID.Win32S) ||
                 (pid == PlatformID.Win32Windows) || (pid == PlatformID.WinCE);
if (isWindows)
{
    const string fontsPath = @"C:\WINDOWS\Fonts";
    Assert.AreEqual(fontsPath.ToLower(),
        SystemFontSource.GetSystemFontFolders().FirstOrDefault()?.ToLower());
}

foreach (string systemFontFolder in SystemFontSource.GetSystemFontFolders())
{
    Console.WriteLine(systemFontFolder);
}

// 设置一种存在于 Windows 字体目录中的字体来替代不存在的字体。
doc.FontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;
doc.FontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Kreon-Regular", new[] {"Calibri"});

Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
Assert.Contains("Calibri",
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").ToArray());

// 或者，我们可以添加一个文件夹字体源，其中相应的文件夹包含字体。
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
doc.FontSettings.SetFontsSources(new FontSourceBase[] {systemFontSource, folderFontSource});
Assert.AreEqual(2, doc.FontSettings.GetFontsSources().Length);

// 重置字体源仍然给我们留下系统字体源以及我们的替代品。
doc.FontSettings.ResetFontSources();

Assert.AreEqual(1, doc.FontSettings.GetFontsSources().Length);
Assert.AreEqual(FontSourceType.SystemFonts, doc.FontSettings.GetFontsSources()[0].Type);
Assert.AreEqual(1,
    doc.FontSettings.SubstitutionSettings.TableSubstitution.GetSubstitutes("Kreon-Regular").Count());
```

### 也可以看看

* 命名空间 [Aspose.Words.Fonts](../../aspose.words.fonts/)
* 部件 [Aspose.Words](../../)


