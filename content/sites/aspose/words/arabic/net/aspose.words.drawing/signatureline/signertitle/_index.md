---
title: SignatureLine.SignerTitle
second_title: Aspose.Words لمراجع .NET API
description: SignatureLine ملكية. الحصول على أو تعيين عنوان الموقّع المقترح على سبيل المثال  المدير . القيمة الافتراضية لهذه الخاصية هي سلسلة فارغة Empty  .
type: docs
weight: 110
url: /ar/net/aspose.words.drawing/signatureline/signertitle/
---
## SignatureLine.SignerTitle property

الحصول على أو تعيين عنوان الموقّع المقترح (على سبيل المثال ، المدير) . القيمة الافتراضية لهذه الخاصية هي **سلسلة فارغة** (Empty ) .

```csharp
public string SignerTitle { get; set; }
```

### أمثلة

يوضح كيفية إنشاء سطر للتوقيع وإدراجه في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

SignatureLineOptions options = new SignatureLineOptions
{
    AllowComments = true,
    DefaultInstructions = true,
    Email = "john.doe@management.com",
    Instructions = "Please sign here",
    ShowDate = true,
    Signer = "John Doe",
    SignerTitle = "Senior Manager"
};

// أدخل شكلًا يحتوي على سطر توقيع ، سنظهر مظهره
// تخصيص باستخدام كائن "SignatureLineOptions" الذي أنشأناه أعلاه.
// إذا أدخلنا شكلًا تنشأ إحداثياته في الركن الأيمن السفلي من الصفحة ،
// سنحتاج إلى توفير إحداثيات سالبة س و ص لإبراز الشكل.
Shape shape = builder.InsertSignatureLine(options, RelativeHorizontalPosition.RightMargin, -170.0, 
        RelativeVerticalPosition.BottomMargin, -60.0, WrapType.None);

Assert.True(shape.IsSignatureLine);

// تحقق من خصائص خط التوقيع الخاص بنا عبر كائن الشكل الخاص به.
SignatureLine signatureLine = shape.SignatureLine;

Assert.AreEqual("john.doe@management.com", signatureLine.Email);
Assert.AreEqual("John Doe", signatureLine.Signer);
Assert.AreEqual("Senior Manager", signatureLine.SignerTitle);
Assert.AreEqual("Please sign here", signatureLine.Instructions);
Assert.True(signatureLine.ShowDate);
Assert.True(signatureLine.AllowComments);
Assert.True(signatureLine.DefaultInstructions);

doc.Save(ArtifactsDir + "Shape.SignatureLine.docx");
```

### أنظر أيضا

* class [SignatureLine](../)
* مساحة الاسم [Aspose.Words.Drawing](../../signatureline/)
* المجسم [Aspose.Words](../../../)


