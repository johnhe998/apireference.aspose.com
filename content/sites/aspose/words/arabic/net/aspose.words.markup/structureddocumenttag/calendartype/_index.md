---
title: StructuredDocumentTag.CalendarType
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag ملكية. تحديد نوع التقويم لهذا المعاملة الخاصة والتفضيلية . الافتراضي هوDefault
type: docs
weight: 50
url: /ar/net/aspose.words.markup/structureddocumenttag/calendartype/
---
## StructuredDocumentTag.CalendarType property

تحديد نوع التقويم لهذا **المعاملة الخاصة والتفضيلية** . الافتراضي هوDefault

```csharp
public SdtCalendarType CalendarType { get; set; }
```

### ملاحظات

الوصول إلى هذه الخاصية سيعمل فقط من أجلDate نوع SDT .

سيحدث استثناء لجميع أنواع المعاملة الخاصة والتفضيلية الأخرى.

### أمثلة

يوضح كيفية مطالبة المستخدم بإدخال تاريخ بعلامة مستند منظم.

```csharp
Document doc = new Document();

// أدخل علامة مستند منظم تطالب المستخدم بإدخال تاريخ.
// في Microsoft Word ، يُعرف هذا العنصر باسم "عنصر تحكم محتوى منتقي التاريخ".
// عندما نضغط على السهم الموجود في الطرف الأيمن من هذه العلامة في Microsoft Word ،
// سنرى نافذة منبثقة في شكل تقويم قابل للنقر.
// يمكننا استخدام تلك النافذة المنبثقة لتحديد التاريخ الذي ستعرضه العلامة.
StructuredDocumentTag sdtDate = new StructuredDocumentTag(doc, SdtType.Date, MarkupLevel.Inline);

// عرض التاريخ حسب اللغة العربية السعودية.
sdtDate.DateDisplayLocale = CultureInfo.GetCultureInfo("ar-SA").LCID;

// اضبط التنسيق الذي تريد عرض التاريخ به.
sdtDate.DateDisplayFormat = "dd MMMM, yyyy";
sdtDate.DateStorageFormat = SdtDateStorageFormat.DateTime;

// عرض التاريخ حسب التقويم الهجري.
sdtDate.CalendarType = SdtCalendarType.Hijri;

// قبل أن يختار المستخدم تاريخًا في Microsoft Word ، ستعرض العلامة النص "انقر هنا لإدخال تاريخ.".
// وفقًا لتقويم العلامة ، قم بتعيين الخاصية "FullDate" للحصول على العلامة لعرض التاريخ الافتراضي.
sdtDate.FullDate = new DateTime(1440, 10, 20);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(sdtDate);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Date.docx");
```

### أنظر أيضا

* enum [SdtCalendarType](../../sdtcalendartype/)
* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


