---
title: SaveOptions.PrettyFormat
second_title: Aspose.Words for .NET API 参考
description: SaveOptions 财产. 什么时候真的  在适用的情况下输出漂亮的格式 默认值为 错误的.
type: docs
weight: 120
url: /zh/net/aspose.words.saving/saveoptions/prettyformat/
---
## SaveOptions.PrettyFormat property

什么时候`真的` , 在适用的情况下输出漂亮的格式。 默认值为 **错误的**.

```csharp
public bool PrettyFormat { get; set; }
```

### 评论

调成 **真的**使 HTML、MHTML、EPUB、WordML、RTF、DOCX 和 ODT 输出具有人类可读性。 用于测试或调试。

### 例子

展示如何增强已保存 .html 文档的原始代码的可读性。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

HtmlSaveOptions htmlOptions = new HtmlSaveOptions(SaveFormat.Html) { PrettyFormat = usePrettyFormat };

doc.Save(ArtifactsDir + "HtmlSaveOptions.PrettyFormat.html", htmlOptions);

// 启用漂亮格式通过添加制表位和换行符使原始 html 代码更具可读性。
string html = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.PrettyFormat.html");

if (usePrettyFormat)
    Assert.AreEqual(
        "<html>\r\n" +
                    "\t<head>\r\n" +
                        "\t\t<meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\" />\r\n" +
                        "\t\t<meta http-equiv=\"Content-Style-Type\" content=\"text/css\" />\r\n" +
                        $"\t\t<meta name=\"generator\" content=\"{BuildVersionInfo.Product} {BuildVersionInfo.Version}\" />\r\n" +
                        "\t\t<title>\r\n" +
                        "\t\t</title>\r\n" +
                    "\t</head>\r\n" +
                    "\t<body style=\"font-family:'Times New Roman'; font-size:12pt\">\r\n" +
                        "\t\t<div>\r\n" +
                            "\t\t\t<p style=\"margin-top:0pt; margin-bottom:0pt\">\r\n" +
                                "\t\t\t\t<span>Hello world!</span>\r\n" +
                            "\t\t\t</p>\r\n" +
                            "\t\t\t<p style=\"margin-top:0pt; margin-bottom:0pt\">\r\n" +
                                "\t\t\t\t<span style=\"-aw-import:ignore\">&#xa0;</span>\r\n" +
                            "\t\t\t</p>\r\n" +
                        "\t\t</div>\r\n" +
                    "\t</body>\r\n</html>", 
        html);
else
    Assert.AreEqual(
        "<html><head><meta http-equiv=\"Content-Type\" content=\"text/html; charset=utf-8\" />" +
                "<meta http-equiv=\"Content-Style-Type\" content=\"text/css\" />" +
                $"<meta name=\"generator\" content=\"{BuildVersionInfo.Product} {BuildVersionInfo.Version}\" /><title></title></head>" +
                "<body style=\"font-family:'Times New Roman'; font-size:12pt\">" +
                "<div><p style=\"margin-top:0pt; margin-bottom:0pt\"><span>Hello world!</span></p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt\"><span style=\"-aw-import:ignore\">&#xa0;</span></p></div></body></html>", 
        html);
```

### 也可以看看

* class [SaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../saveoptions/)
* 部件 [Aspose.Words](../../../)


