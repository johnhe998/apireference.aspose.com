---
title: Enum ViewType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Settings.ViewType تعداد. القيم المحتملة لوضع العرض في Microsoft Word.
type: docs
weight: 5660
url: /ar/net/aspose.words.settings/viewtype/
---
## ViewType enumeration

القيم المحتملة لوضع العرض في Microsoft Word.

```csharp
public enum ViewType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | يجب تقديم المستند في طريقة العرض الافتراضية للتطبيق. |
| Reading | `0` | يجب تقديم المستند في طريقة العرض الافتراضية للتطبيق. |
| PageLayout | `1` | يجب فتح المستند بطريقة تعرض المستند كما سيتم طباعته. |
| Outline | `3` | يجب تقديم المستند بطريقة عرض محسّنة لتخطيط أو إنشاء مستندات طويلة. |
| Normal | `4` | يجب تقديم المستند بطريقة عرض محسّنة لتخطيط أو إنشاء مستندات طويلة. |
| Web | `5` | يجب تقديم المستند بطريقة عرض تحاكي الطريقة التي سيتم بها عرض هذا المستند في صفحة ويب . |

### أمثلة

يوضح كيفية تعيين عامل تكبير مخصص ، أي الإصدارات القديمة من Microsoft Word سيتم تطبيقها على مستند عند التحميل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

Assert.AreEqual(ZoomType.Custom, doc.ViewOptions.ZoomType);
Assert.AreEqual(ZoomType.None, doc.ViewOptions.ZoomType);

doc.Save(ArtifactsDir + "ViewOptions.SetZoomPercentage.doc");
```

### أنظر أيضا

* class [ViewOptions](../viewoptions/)
* property [ViewType](../viewoptions/viewtype/)
* مساحة الاسم [Aspose.Words.Settings](../../aspose.words.settings/)
* المجسم [Aspose.Words](../../)


