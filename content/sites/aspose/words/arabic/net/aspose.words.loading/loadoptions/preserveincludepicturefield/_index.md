---
title: LoadOptions.PreserveIncludePictureField
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. الحصول على أو تحديد ما إذا كان سيتم الاحتفاظ بحقل INCLUDEPICTURE عند قراءة تنسيقات Microsoft Word . القيمة الافتراضية هي false .
type: docs
weight: 120
url: /ar/net/aspose.words.loading/loadoptions/preserveincludepicturefield/
---
## LoadOptions.PreserveIncludePictureField property

الحصول على أو تحديد ما إذا كان سيتم الاحتفاظ بحقل INCLUDEPICTURE عند قراءة تنسيقات Microsoft Word . القيمة الافتراضية هي false .

```csharp
public bool PreserveIncludePictureField { get; set; }
```

### ملاحظات

بشكل افتراضي ، يتم تحويل حقل INCLUDEPICTURE إلى كائن شكل. يمكنك تجاوز ذلك إذا كنت need الحقل المطلوب الاحتفاظ به ، على سبيل المثال ، إذا كنت ترغب في تحديثه برمجيًا. لاحظ مع ذلك أن هذا الأسلوب ليس شائعًا بالنسبة لـ Aspose.Words. استخدمه على مسؤوليتك الخاصة.

قد تكون إحدى حالات الاستخدام المحتملة هي استخدام MERGEFIELD كحقل فرعي لتغيير مسار مصدر الصورة بشكل ديناميكي. في هذه الحالة ، تحتاج إلى الاحتفاظ بـ INCLUDEPICTURE في النموذج.

### أمثلة

يوضح كيفية الاحتفاظ بحقول INCLUDEPICTURE أو تجاهلها عند تحميل مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldIncludePicture includePicture = (FieldIncludePicture)builder.InsertField(FieldType.FieldIncludePicture, true);
includePicture.SourceFullName = ImageDir + "Transparent background logo.png";
includePicture.Update(true);

using (MemoryStream docStream = new MemoryStream())
{
    doc.Save(docStream, new OoxmlSaveOptions(SaveFormat.Docx));

    // يمكننا تعيين علامة في كائن LoadOptions لتحديد ما إذا كان سيتم تحويل جميع حقول INCLUDEPICTURE
    // في أشكال الصور عند تحميل مستند يحتوي عليها.
    LoadOptions loadOptions = new LoadOptions
    {
        PreserveIncludePictureField = preserveIncludePictureField
    };

    doc = new Document(docStream, loadOptions);

    if (preserveIncludePictureField)
    {
        Assert.True(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));

        doc.UpdateFields();
        doc.Save(ArtifactsDir + "Field.PreserveIncludePicture.docx");
    }
    else
    {
        Assert.False(doc.Range.Fields.Any(f => f.Type == FieldType.FieldIncludePicture));
    }
}
```

### أنظر أيضا

* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


