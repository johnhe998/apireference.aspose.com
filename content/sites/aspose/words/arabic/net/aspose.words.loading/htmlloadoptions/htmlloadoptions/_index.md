---
title: HtmlLoadOptions.HtmlLoadOptions
second_title: Aspose.Words لمراجع .NET API
description: HtmlLoadOptions البناء. تهيئة مثيل جديد لهذه الفئة بالقيم الافتراضية.
type: docs
weight: 10
url: /ar/net/aspose.words.loading/htmlloadoptions/htmlloadoptions/
---
## HtmlLoadOptions() {#constructor}

تهيئة مثيل جديد لهذه الفئة بالقيم الافتراضية.

```csharp
public HtmlLoadOptions()
```

### أمثلة

يوضح كيفية دعم التعليقات الشرطية أثناء تحميل مستند HTML.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// إذا كانت القيمة صحيحة ، فإننا نأخذ كود VML في الاعتبار أثناء تحليل المستند الذي تم تحميله.
loadOptions.SupportVml = supportVml;

// يحتوي هذا المستند على صورة JPEG ضمن "<! - [if gte vml 1] >" العلامات
// وصورة PNG مختلفة داخل "<! [if! vml] >" العلامات.
// إذا قمنا بتعيين علامة "SupportVml" على "true" ، فستقوم Aspose.Words بتحميل JPEG.
// إذا قمنا بتعيين هذه العلامة على "خطأ" ، فإن Aspose.Words سوف يقوم بتحميل PNG فقط.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### أنظر أيضا

* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)

---

## HtmlLoadOptions(string) {#constructor_2}

اختصار لتهيئة مثيل جديد من هذه الفئة بكلمة المرور المحددة لتحميل مستند مشفر.

```csharp
public HtmlLoadOptions(string password)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| password | String | كلمة السر لفتح وثيقة مشفرة. يمكن أن تكون سلسلة فارغة أو فارغة. |

### أمثلة

يوضح كيفية تشفير مستند Html ، ثم فتحه باستخدام كلمة مرور.

```csharp
// إنشاء وتوقيع مستند HTML مشفر من ملف docx. مشفر.
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

// لتحميل هذا المستند وقراءته ، سنحتاج إلى تمرير فك تشفيره
// كلمة المرور باستخدام كائن HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions("docPassword");

Assert.AreEqual(signOptions.DecryptionPassword, loadOptions.Password);

Document doc = new Document(outputFileName, loadOptions);

Assert.AreEqual("Test encrypted document.", doc.GetText().Trim());
```

### أنظر أيضا

* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)

---

## HtmlLoadOptions(LoadFormat, string, string) {#constructor_1}

اختصار لتهيئة مثيل جديد من هذه الفئة بخصائص معينة للقيم المحددة.

```csharp
public HtmlLoadOptions(LoadFormat loadFormat, string password, string baseUri)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| loadFormat | LoadFormat | تنسيق المستند المراد تحميله. |
| password | String | كلمة السر لفتح وثيقة مشفرة. يمكن أن تكون سلسلة فارغة أو فارغة. |
| baseUri | String | السلسلة التي سيتم استخدامها لحل محددات URI النسبية إلى مطلقة. يمكن أن تكون سلسلة فارغة أو فارغة. |

### أمثلة

يوضح كيفية تحديد عنوان URI أساسي عند فتح مستند html.

```csharp
// لنفترض أننا نريد تحميل مستند .html يحتوي على صورة مرتبطة بواسطة URI نسبي
// أثناء وجود الصورة في موقع مختلف. في هذه الحالة ، سنحتاج إلى حل URI النسبي إلى واحد مطلق.
 // يمكننا توفير URI أساسي باستخدام كائن HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// بينما كانت الصورة معطلة في الإدخال .html ، ساعدنا URI المخصص في إصلاح الرابط.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// سيعرض هذا المستند الناتج الصورة المفقودة.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### أنظر أيضا

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)


