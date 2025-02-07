---
title: StructuredDocumentTag.Checked
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag ملكية. يحصل / يحدد الحالة الحالية لمربع الاختيار المعاملة الخاصة والتفضيلية . القيمة الافتراضية لهذه الخاصية خاطئة.
type: docs
weight: 60
url: /ar/net/aspose.words.markup/structureddocumenttag/checked/
---
## StructuredDocumentTag.Checked property

يحصل / يحدد الحالة الحالية لمربع الاختيار **المعاملة الخاصة والتفضيلية** . القيمة الافتراضية لهذه الخاصية خاطئة.

```csharp
public bool Checked { get; set; }
```

### ملاحظات

الوصول إلى هذه الخاصية سيعمل فقط من أجلCheckbox أنواع SDT .

سيحدث استثناء لجميع أنواع المعاملة الخاصة والتفضيلية الأخرى.

### أمثلة

أظهر كيفية إنشاء علامة وثيقة منظمة في شكل خانة اختيار.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

StructuredDocumentTag sdtCheckBox =
    new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline) {Checked = true};

// يمكننا تعيين الرموز المستخدمة لتمثيل الحالة المحددة / غير المحددة لعنصر تحكم محتوى مربع الاختيار.
sdtCheckBox.SetCheckedSymbol(0x00A9, "Times New Roman");
sdtCheckBox.SetUncheckedSymbol(0x00AE, "Times New Roman");

builder.InsertNode(sdtCheckBox);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CheckBox.docx");
```

### أنظر أيضا

* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


