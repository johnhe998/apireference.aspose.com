---
title: TableSubstitutionRule.Load
second_title: Aspose.Words for .NET API 参考
description: TableSubstitutionRule 方法. 从 XML 文件加载表替换设置
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/tablesubstitutionrule/load/
---
## Load(string) {#load_1}

从 XML 文件加载表替换设置。

```csharp
public void Load(string fileName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| fileName | String | 输入文件名。 |

### 例子

展示如何使用自定义字体替换表。

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// 创建一个新的表替换规则并加载默认的 Windows 字体替换表。
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;

// 如果我们只从我们的文件夹中选择字体，我们将需要一个自定义替换表。
// 我们将无法再访问 Microsoft Windows 字体，
// 例如“Arial”或“Times New Roman”，因为它们不存在于我们的新字体文件夹中。
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// 下面是从本地文件系统中的文件加载替换表的两种方法。
// 1 - 来自流：
using (FileStream fileStream = new FileStream(MyDir + "Font substitution rules.xml", FileMode.Open))
{
    tableSubstitutionRule.Load(fileStream);
}

// 2 - 直接来自文件：
tableSubstitutionRule.Load(MyDir + "Font substitution rules.xml");

// 由于我们不再可以访问“Arial”，我们的字体表将首先尝试将其替换为“Nonexistent Font”。
// 我们没有这个字体，所以它会移动到下一个替代品，“Kreon”，在“MyFonts”文件夹中找到。
Assert.AreEqual(new[] {"Missing Font", "Kreon"}, tableSubstitutionRule.GetSubstitutes("Arial").ToArray());

// 我们可以通过编程方式扩展这个表。我们将添加一个条目，将“Times New Roman”替换为“Arvo”
Assert.Null(tableSubstitutionRule.GetSubstitutes("Times New Roman"));
tableSubstitutionRule.AddSubstitutes("Times New Roman", "Arvo");
Assert.AreEqual(new[] {"Arvo"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// 我们可以使用 AddSubstitutes() 为现有字体条目添加辅助备用替代品。
// 如果“Arvo”不可用，我们的表格将寻找“M+2m”作为第二个替代选项。
tableSubstitutionRule.AddSubstitutes("Times New Roman", "M+ 2m");
Assert.AreEqual(new[] {"Arvo", "M+ 2m"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// SetSubstitutes() 可以为字体设置一个新的替代字体列表。
tableSubstitutionRule.SetSubstitutes("Times New Roman", new[] {"Squarish Sans CT", "M+ 2m"});
Assert.AreEqual(new[] {"Squarish Sans CT", "M+ 2m"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// 以我们无权访问的字体编写文本将调用我们的替换规则。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("Text written in Arial, to be substituted by Kreon.");

builder.Font.Name = "Times New Roman";
builder.Writeln("Text written in Times New Roman, to be substituted by Squarish Sans CT.");

doc.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Custom.pdf");
```

### 也可以看看

* class [TableSubstitutionRule](../)
* 命名空间 [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* 部件 [Aspose.Words](../../../)

---

## Load(Stream) {#load}

从 XML 流加载表替换设置。

```csharp
public void Load(Stream stream)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| stream | Stream | 输入流。 |

### 例子

展示如何使用自定义字体替换表。

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// 创建一个新的表替换规则并加载默认的 Windows 字体替换表。
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;

// 如果我们只从我们的文件夹中选择字体，我们将需要一个自定义替换表。
// 我们将无法再访问 Microsoft Windows 字体，
// 例如“Arial”或“Times New Roman”，因为它们不存在于我们的新字体文件夹中。
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// 下面是从本地文件系统中的文件加载替换表的两种方法。
// 1 - 来自流：
using (FileStream fileStream = new FileStream(MyDir + "Font substitution rules.xml", FileMode.Open))
{
    tableSubstitutionRule.Load(fileStream);
}

// 2 - 直接来自文件：
tableSubstitutionRule.Load(MyDir + "Font substitution rules.xml");

// 由于我们不再可以访问“Arial”，我们的字体表将首先尝试将其替换为“Nonexistent Font”。
// 我们没有这个字体，所以它会移动到下一个替代品，“Kreon”，在“MyFonts”文件夹中找到。
Assert.AreEqual(new[] {"Missing Font", "Kreon"}, tableSubstitutionRule.GetSubstitutes("Arial").ToArray());

// 我们可以通过编程方式扩展这个表。我们将添加一个条目，将“Times New Roman”替换为“Arvo”
Assert.Null(tableSubstitutionRule.GetSubstitutes("Times New Roman"));
tableSubstitutionRule.AddSubstitutes("Times New Roman", "Arvo");
Assert.AreEqual(new[] {"Arvo"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// 我们可以使用 AddSubstitutes() 为现有字体条目添加辅助备用替代品。
// 如果“Arvo”不可用，我们的表格将寻找“M+2m”作为第二个替代选项。
tableSubstitutionRule.AddSubstitutes("Times New Roman", "M+ 2m");
Assert.AreEqual(new[] {"Arvo", "M+ 2m"}, tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// SetSubstitutes() 可以为字体设置一个新的替代字体列表。
tableSubstitutionRule.SetSubstitutes("Times New Roman", new[] {"Squarish Sans CT", "M+ 2m"});
Assert.AreEqual(new[] {"Squarish Sans CT", "M+ 2m"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman").ToArray());

// 以我们无权访问的字体编写文本将调用我们的替换规则。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("Text written in Arial, to be substituted by Kreon.");

builder.Font.Name = "Times New Roman";
builder.Writeln("Text written in Times New Roman, to be substituted by Squarish Sans CT.");

doc.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Custom.pdf");
```

### 也可以看看

* class [TableSubstitutionRule](../)
* 命名空间 [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* 部件 [Aspose.Words](../../../)


