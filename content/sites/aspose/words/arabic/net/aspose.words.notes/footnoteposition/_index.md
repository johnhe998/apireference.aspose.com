---
title: Enum FootnotePosition
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Notes.FootnotePosition تعداد. يحدد موضع الحاشية السفلية .
type: docs
weight: 4050
url: /ar/net/aspose.words.notes/footnoteposition/
---
## FootnotePosition enumeration

يحدد موضع الحاشية السفلية .

```csharp
public enum FootnotePosition
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| BottomOfPage | `1` | يتم إخراج الحواشي السفلية في أسفل كل صفحة. |
| BeneathText | `2` | يتم إخراج الحواشي السفلية أسفل النص في كل صفحة. |

### أمثلة

يوضح كيفية تحديد مكان مختلف حيث يجمع المستند ويعرض الحواشي السفلية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// الحاشية السفلية هي طريقة لإرفاق مرجع أو تعليق جانبي بالنص
// لا يتعارض مع انسياب النص الأساسي الرئيسي.  
// يؤدي إدراج حاشية سفلية إلى إضافة رمز مرجعي صغير مرتفع
// في النص الأساسي الرئيسي حيث نقوم بإدخال الحاشية السفلية.
// تقوم كل حاشية سفلية أيضًا بإنشاء إدخال في أسفل الصفحة ، يتكون من رمز
// الذي يطابق رمز المرجع في النص الأساسي الرئيسي.
// النص المرجعي الذي نمرره إلى طريقة "InsertFootnote" الخاصة بمنشئ المستندات.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote contents.");

// يمكننا استخدام خاصية "الموضع" لتحديد المكان الذي ستضع فيه الوثيقة جميع حواشيها السفلية.
// إذا قمنا بتعيين قيمة خاصية "الموضع" على "FootnotePosition.BottomOfPage" ،
// ستظهر كل حاشية سفلية في أسفل الصفحة التي تحتوي على علامتها المرجعية. هذه هي القيمة الافتراضية.
// إذا قمنا بتعيين قيمة خاصية "الموضع" على "FootnotePosition.BeneathText" ،
// ستظهر كل حاشية سفلية في نهاية نص الصفحة الذي يحتوي على علامتها المرجعية.
doc.FootnoteOptions.Position = footnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionFootnote.docx");
```

### أنظر أيضا

* class [FootnoteOptions](../footnoteoptions/)
* مساحة الاسم [Aspose.Words.Notes](../../aspose.words.notes/)
* المجسم [Aspose.Words](../../)


