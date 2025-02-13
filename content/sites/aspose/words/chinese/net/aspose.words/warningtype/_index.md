---
title: Enum WarningType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.WarningType 枚举. 指定 Aspose.Words 在文档加载或保存期间发出的警告类型
type: docs
weight: 6350
url: /zh/net/aspose.words/warningtype/
---
## WarningType enumeration

指定 Aspose.Words 在文档加载或保存期间发出的警告类型。

```csharp
[Flags]
public enum WarningType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| DataLossCategory | `FF` | 加载后的文档树 或保存后创建的文档中将丢失一些文本/字符/图像或其他数据。 |
| DataLoss | `1` | 通用数据丢失，没有具体代码。 |
| MajorFormattingLossCategory | `FF00` | 生成的文档或其中的特定位置可能看起来与原始文档有很大不同 。 |
| MajorFormattingLoss | `100` | 通用主要格式丢失，没有具体代码。 |
| MinorFormattingLossCategory | `FF0000` | 与原始文档相比， 生成的文档或其中的特定位置可能看起来有些不同。 |
| MinorFormattingLoss | `10000` | 通用次要格式丢失，没有特定代码。 |
| FontSubstitution | `20000` | 字体已被替换。 |
| FontEmbedding | `40000` | 文档保存期间嵌入的字体信息丢失。 |
| UnexpectedContentCategory | `F000000` | 源文档中的某些内容无法识别（即不受支持），这可能会或可能不会 导致问题或导致数据/格式丢失。 |
| UnexpectedContent | `1000000` | 通用的意外内容，没有特定代码。 |
| Hint | `10000000` | 就潜在问题提出建议或提出改进建议。 |

### 例子

演示如何设置属性以从可用字体源中查找缺失字体的最接近匹配项。

```csharp
[Test]
public void EnableFontSubstitution()
{
    // 打开一个文档，其中包含使用我们的任何字体源中都不存在的字体格式化的文本。
    Document doc = new Document(MyDir + "Missing font.docx");

    // 分配一个回调来处理字体替换警告。
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // 设置默认字体名称并启用字体替换。
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // 如果我们保存缺少字体的文档，我们将收到字体替换警告。
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // 我们还可以验证集合中的警告并清除它们。
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// 在加载/保存过程中每次出现警告时调用。
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


