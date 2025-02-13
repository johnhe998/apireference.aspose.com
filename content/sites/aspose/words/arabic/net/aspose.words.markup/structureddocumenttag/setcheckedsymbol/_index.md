---
title: StructuredDocumentTag.SetCheckedSymbol
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag طريقة. يعين الرمز المستخدم لتمثيل الحالة المحددة لعنصر تحكم محتوى خانة الاختيار.
type: docs
weight: 350
url: /ar/net/aspose.words.markup/structureddocumenttag/setcheckedsymbol/
---
## StructuredDocumentTag.SetCheckedSymbol method

يعين الرمز المستخدم لتمثيل الحالة المحددة لعنصر تحكم محتوى خانة الاختيار.

```csharp
public void SetCheckedSymbol(int characterCode, string fontName)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| characterCode | Int32 | رمز الحرف للرمز المحدد. |
| fontName | String | اسم الخط الذي يحتوي على الرمز. |

### ملاحظات

الوصول إلى هذه الطريقة سيعمل فقط من أجلCheckbox أنواع المعاملة الخاصة والتفضيلية.

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


