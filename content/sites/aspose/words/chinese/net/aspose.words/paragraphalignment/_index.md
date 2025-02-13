---
title: Enum ParagraphAlignment
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.ParagraphAlignment 枚举. 指定段落中的文本对齐方式
type: docs
weight: 4160
url: /zh/net/aspose.words/paragraphalignment/
---
## ParagraphAlignment enumeration

指定段落中的文本对齐方式。

```csharp
public enum ParagraphAlignment
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Left | `0` | 文本向左对齐。 |
| Center | `1` | 文本水平居中。 |
| Right | `2` | 文本向右对齐。 |
| Justify | `3` | 文本左右对齐。 |
| Distributed | `4` | 文字分布均匀。 |
| ArabicMediumKashida | `5` | 仅限阿拉伯语。文本的 Kashida 长度扩展为消费者确定的中等长度。 |
| ArabicHighKashida | `7` | 仅限阿拉伯语。文本的 Kashida 长度已扩展到其可能的最大长度。 |
| ArabicLowKashida | `8` | 仅限阿拉伯语。文本的 Kashida 长度被扩展为稍长的长度。 |
| ThaiDistributed | `9` | 仅限泰语。文本通过对 Thai. 的优化来证明是合理的 |
| MathElementCenterAsGroup | `10` | 一行中唯一的数学元素，对齐为“居中作为组”。 |

### 例子

展示如何手动构建 Aspose.Words 文档。

```csharp
Document doc = new Document();

// 一个空白文档包含一个部分、一个正文和一个段落。
// 调用“RemoveAllChildren”方法来移除所有这些节点，
// 最后得到一个没有子节点的文档节点。
doc.RemoveAllChildren();

// 这个文档现在没有我们可以添加内容的复合子节点。
// 如果我们想编辑它，我们需要重新填充它的节点集合。
// 首先，创建一个新部分，然后将其作为子节点附加到根文档节点。
Section section = new Section(doc);
doc.AppendChild(section);

// 为该部分设置一些页面设置属性。
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// 一个section需要一个body，它将包含并显示它的所有内容
// 在节的页眉和页脚之间的页面上。
Body body = new Body(doc);
section.AppendChild(body);

// 创建一个段落，设置一些格式属性，然后将其作为子项附加到正文中。
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// 最后，添加一些内容来做文档。创建运行，
// 设置其外观和内容，然后将其作为子项附加到段落中。
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


