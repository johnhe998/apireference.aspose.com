---
title: Class SignatureLine
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.SignatureLine فصل. يوفر الوصول إلى خصائص سطر التوقيع.
type: docs
weight: 1150
url: /ar/net/aspose.words.drawing/signatureline/
---
## SignatureLine class

يوفر الوصول إلى خصائص سطر التوقيع.

```csharp
public class SignatureLine
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [AllowComments](../../aspose.words.drawing/signatureline/allowcomments/) { get; set; } | الحصول على أو تعيين قيمة تشير إلى أن الموقّع يمكنه إضافة تعليقات في مربع حوار التوقيع . القيمة الافتراضية لهذه الخاصية هي **خاطئة** . |
| [DefaultInstructions](../../aspose.words.drawing/signatureline/defaultinstructions/) { get; set; } | الحصول على قيمة أو تعيينها للإشارة إلى أن الإرشادات الافتراضية تظهر في مربع حوار التوقيع . القيمة الافتراضية لهذه الخاصية هي **حقيقي** . |
| [Email](../../aspose.words.drawing/signatureline/email/) { get; set; } | الحصول على أو تعيين عنوان البريد الإلكتروني للموقّع المقترح. القيمة الافتراضية لهذه الخاصية هي **سلسلة فارغة** (Empty ) . |
| [Id](../../aspose.words.drawing/signatureline/id/) { get; set; } | الحصول على أو تعيين معرف لسطر التوقيع هذا. |
| [Instructions](../../aspose.words.drawing/signatureline/instructions/) { get; set; } | الحصول على التعليمات أو تعيينها للموقِّع التي يتم عرضها عند توقيع سطر التوقيع. يتم تجاهل هذه الخاصية إذا[`DefaultInstructions`](./defaultinstructions/) تم تعيين. القيمة الافتراضية لهذه الخاصية هي **سلسلة فارغة** (Empty ) . |
| [IsSigned](../../aspose.words.drawing/signatureline/issigned/) { get; } | يشير إلى أن سطر التوقيع موقّع بالتوقيع الرقمي. |
| [IsValid](../../aspose.words.drawing/signatureline/isvalid/) { get; } | يشير إلى أن سطر التوقيع موقّع بالتوقيع الرقمي وأن هذا التوقيع الرقمي صالح. |
| [ProviderId](../../aspose.words.drawing/signatureline/providerid/) { get; set; } | الحصول على أو تعيين معرف موفر التوقيع لسطر التوقيع هذا . القيمة الافتراضية هي "{00000000-0000-0000-0000-000000000000}" . |
| [ShowDate](../../aspose.words.drawing/signatureline/showdate/) { get; set; } | الحصول على أو تعيين قيمة تشير إلى أن تاريخ التوقيع يظهر في سطر التوقيع. القيمة الافتراضية لهذه الخاصية هي **حقيقي** . |
| [Signer](../../aspose.words.drawing/signatureline/signer/) { get; set; } | الحصول على أو تعيين المُوقِّع المقترح لسطر التوقيع . القيمة الافتراضية لهذه الخاصية هي **سلسلة فارغة** (Empty ) . |
| [SignerTitle](../../aspose.words.drawing/signatureline/signertitle/) { get; set; } | الحصول على أو تعيين عنوان الموقّع المقترح (على سبيل المثال ، المدير) . القيمة الافتراضية لهذه الخاصية هي **سلسلة فارغة** (Empty ) . |

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

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


