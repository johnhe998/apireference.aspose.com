---
title: Enum MsWordVersion
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Settings.MsWordVersion 枚举. 允许 Aspose.Wods 模仿 MS Word 版本特定的应用程序行为
type: docs
weight: 5560
url: /zh/net/aspose.words.settings/mswordversion/
---
## MsWordVersion enumeration

允许 Aspose.Wods 模仿 MS Word 版本特定的应用程序行为。

```csharp
public enum MsWordVersion
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Word2000 | `0` | 优化 Aspose.Words 行为以匹配 MS Word 2000 版本。 |
| Word2002 | `1` | 优化 Aspose.Words 行为以匹配 MS Word 2002 版本。 |
| Word2003 | `2` | 优化 Aspose.Words 行为以匹配 MS Word 2003 版本。 |
| Word2007 | `3` | 优化 Aspose.Words 行为以匹配 MS Word 2007 版本。 |
| Word2010 | `4` | 优化 Aspose.Words 行为以匹配 MS Word 2010 版本。 |
| Word2013 | `5` | 优化 Aspose.Words 行为以匹配 MS Word 2013 版本。 |
| Word2016 | `6` | 优化 Aspose.Words 行为以匹配 MS Word 2016 版本。 |
| Word2019 | `7` | 优化 Aspose.Words 行为以匹配 MS Word 2019 版本。 |

### 例子

展示如何针对不同版本的 Microsoft Word 优化文档。

```csharp
public void OptimizeFor()
{
    Document doc = new Document();

    // 此对象包含每个文档唯一的大量标志列表
    // 这使我们能够促进与旧版本的 Microsoft Word 的向后兼容性。
    CompatibilityOptions options = doc.CompatibilityOptions;

    // 打印空白文档的默认设置。
    Console.WriteLine("\nDefault optimization settings:");
    PrintCompatibilityOptions(options);

    // 我们可以在 Microsoft Word 中通过“文件”访问这些设置 -> “选项”-> “高级”-> “...的兼容性选项”。
    doc.Save(ArtifactsDir + "CompatibilityOptions.OptimizeFor.DefaultSettings.docx");

    // 我们可以使用 OptimizeFor 方法来确保与特定 Microsoft Word 版本的最佳兼容性。
    doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
    Console.WriteLine("\nOptimized for Word 2010:");
    PrintCompatibilityOptions(options);

    doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2000);
    Console.WriteLine("\nOptimized for Word 2000:");
    PrintCompatibilityOptions(options);
}

/// <summary>
/// 按状态对文档的兼容性选项对象中的所有标志进行分组，然后打印每个组。
/// </summary>
private static void PrintCompatibilityOptions(CompatibilityOptions options)
{
    for (int i = 1; i >= 0; i--)
    {
        Console.WriteLine(Convert.ToBoolean(i) ? "\tEnabled options:" : "\tDisabled options:");
        SortedSet<string> optionNames = new SortedSet<string>();

        foreach (System.ComponentModel.PropertyDescriptor descriptor in System.ComponentModel.TypeDescriptor.GetProperties(options))
        {
            if (descriptor.PropertyType == Type.GetType("System.Boolean") && i == Convert.ToInt32(descriptor.GetValue(options)))
            {
                optionNames.Add(descriptor.Name);
            }
        }

        foreach (string s in optionNames)
        {
            Console.WriteLine($"\t\t{s}");
        }
    }
}
```

### 也可以看看

* 命名空间 [Aspose.Words.Settings](../../aspose.words.settings/)
* 部件 [Aspose.Words](../../)


