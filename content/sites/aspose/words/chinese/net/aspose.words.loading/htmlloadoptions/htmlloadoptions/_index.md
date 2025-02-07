---
title: HtmlLoadOptions.HtmlLoadOptions
second_title: Aspose.Words for .NET API 参考
description: HtmlLoadOptions 构造函数. 使用默认值初始化此类的新实例
type: docs
weight: 10
url: /zh/net/aspose.words.loading/htmlloadoptions/htmlloadoptions/
---
## HtmlLoadOptions() {#constructor}

使用默认值初始化此类的新实例。

```csharp
public HtmlLoadOptions()
```

### 例子

展示如何在加载 HTML 文档时支持条件注释。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// 如果值为真，那么我们在解析加载的文档时会考虑 VML 代码。
loadOptions.SupportVml = supportVml;

// 此文档在“<!--[if gte vml 1]>”中包含一个 JPEG 图像标签，
// 以及 "<![if !vml]>" 中的不同 PNG 图像标签。
// 如果我们将“SupportVml”标志设置为“true”，那么 Aspose.Words 将加载 JPEG。
// 如果我们将此标志设置为“false”，那么 Aspose.Words 将只加载 PNG。
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### 也可以看看

* class [HtmlLoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../htmlloadoptions/)
* 部件 [Aspose.Words](../../../)

---

## HtmlLoadOptions(string) {#constructor_2}

使用指定密码初始化此类的新实例以加载加密文档的快捷方式。

```csharp
public HtmlLoadOptions(string password)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| password | String | 打开加密文档的密码。可以是 null 或空字符串。 |

### 例子

演示如何加密 Html 文档，然后使用密码打开它。

```csharp
// 从加密的 .docx 创建并签署加密的 HTML 文档。
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "HtmlLoadOptions.EncryptedHtml.html";
DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);

// 要加载和阅读这个文档，我们需要通过它的解密
// 使用 HtmlLoadOptions 对象的密码。
HtmlLoadOptions loadOptions = new HtmlLoadOptions("docPassword");

Assert.AreEqual(signOptions.DecryptionPassword, loadOptions.Password);

Document doc = new Document(outputFileName, loadOptions);

Assert.AreEqual("Test encrypted document.", doc.GetText().Trim());
```

### 也可以看看

* class [HtmlLoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../htmlloadoptions/)
* 部件 [Aspose.Words](../../../)

---

## HtmlLoadOptions(LoadFormat, string, string) {#constructor_1}

使用设置为指定值的属性初始化此类的新实例的快捷方式。

```csharp
public HtmlLoadOptions(LoadFormat loadFormat, string password, string baseUri)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| loadFormat | LoadFormat | 要加载的文档的格式。 |
| password | String | 打开加密文档的密码。可以是 null 或空字符串。 |
| baseUri | String | 将用于将相对 URI 解析为绝对的字符串。可以是 null 或空字符串。 |

### 例子

演示如何在打开 html 文档时指定基本 URI。

```csharp
// 假设我们要加载一个 .html 文档，其中包含一个由相对 URI 链接的图像
// 当图像在不同的位置时。在这种情况下，我们需要将相对 URI 解析为绝对 URI。
 // 我们可以使用 HtmlLoadOptions 对象提供基本 URI。
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// 当输入 .html 中的图像损坏时，我们的自定义基本 URI 帮助我们修复了链接。
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// 此输出文档将显示丢失的图像。
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### 也可以看看

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [HtmlLoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../htmlloadoptions/)
* 部件 [Aspose.Words](../../../)


