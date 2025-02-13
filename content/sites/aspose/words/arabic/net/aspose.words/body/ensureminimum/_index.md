---
title: Body.EnsureMinimum
second_title: Aspose.Words لمراجع .NET API
description: Body طريقة. إذا لم يكن الطفل الأخير فقرة  فسيتم إنشاء وإلحاق فقرة واحدة فارغة.
type: docs
weight: 50
url: /ar/net/aspose.words/body/ensureminimum/
---
## Body.EnsureMinimum method

إذا لم يكن الطفل الأخير فقرة ، فسيتم إنشاء وإلحاق فقرة واحدة فارغة.

```csharp
public void EnsureMinimum()
```

### أمثلة

يمسح النص الرئيسي من جميع أقسام المستند مع ترك الأقسام نفسها.

```csharp
Document doc = new Document();

// يحتوي المستند الفارغ على قسم واحد وجسم واحد وفقرة واحدة.
// اتصل بطريقة "RemoveAllChildren" لإزالة كل هذه العقد ،
// وتنتهي بعقدة مستند بدون توابع.
doc.RemoveAllChildren();

// لا يحتوي هذا المستند الآن على عقد فرعية مركبة يمكننا إضافة محتوى إليها.
// إذا كنا نرغب في تعديله ، فسنحتاج إلى إعادة ملء مجموعة العقد الخاصة به.
// أولاً ، قم بإنشاء قسم جديد ، ثم قم بإلحاقه كعقدة فرعية بصفته فرعيًا.
Section section = new Section(doc);
doc.AppendChild(section);

// يحتاج القسم إلى جسم يحتوي على جميع محتوياته ويعرضها
// في الصفحة الواقعة بين رأس وتذييل القسم.
Body body = new Body(doc);
section.AppendChild(body);

// هذا الجسد ليس له أطفال ، لذا لا يمكننا إضافة أشواط إليه حتى الآن.
Assert.AreEqual(0, doc.FirstSection.Body.GetChildNodes(NodeType.Any, true).Count);

// اتصل بـ "WarrantyMinimum" للتأكد من أن هذا النص يحتوي على فقرة فارغة واحدة على الأقل. 
body.EnsureMinimum();

// الآن ، يمكننا إضافة عمليات التشغيل إلى النص ، والحصول على المستند لعرضها.
body.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### أنظر أيضا

* class [Body](../)
* مساحة الاسم [Aspose.Words](../../body/)
* المجسم [Aspose.Words](../../../)


