---
title: Enum ParagraphAlignment
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ParagraphAlignment تعداد. يحدد محاذاة النص في فقرة .
type: docs
weight: 4160
url: /ar/net/aspose.words/paragraphalignment/
---
## ParagraphAlignment enumeration

يحدد محاذاة النص في فقرة .

```csharp
public enum ParagraphAlignment
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Left | `0` | يتم محاذاة النص إلى اليسار . |
| Center | `1` | يتم توسيط النص أفقيًا . |
| Right | `2` | يتم محاذاة النص إلى اليمين. |
| Justify | `3` | تمت محاذاة النص إلى اليسار واليمين . |
| Distributed | `4` | يتم توزيع النص بالتساوي. |
| ArabicMediumKashida | `5` | عربي فقط. يتم تمديد طول الكشيدة للنص إلى متوسط الطول الذي يحدده المستهلك. |
| ArabicHighKashida | `7` | عربي فقط. يتم تمديد طول الكشيدة للنص إلى أكبر طول ممكن. |
| ArabicLowKashida | `8` | عربي فقط. يتم تمديد طول الكشيدة للنص إلى طول أطول قليلاً . |
| ThaiDistributed | `9` | التايلاندية فقط. النص مبرر بتحسين اللغة التايلاندية. |
| MathElementCenterAsGroup | `10` | العنصر الرياضي الوحيد في السطر ، تمت محاذاته كـ "توسيط كمجموعة" . |

### أمثلة

يوضح كيفية إنشاء مستند Aspose.Words يدويًا.

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

// تعيين بعض خصائص إعداد الصفحة للقسم.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// يحتاج القسم إلى جسم يحتوي على جميع محتوياته ويعرضها
// في الصفحة الواقعة بين رأس وتذييل القسم.
Body body = new Body(doc);
section.AppendChild(body);

// قم بإنشاء فقرة ، وقم بتعيين بعض خصائص التنسيق ، ثم قم بإلحاقها كطفل بالجسم.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// أخيرًا ، أضف بعض المحتوى لعمل المستند. إنشاء شوط ،
// قم بتعيين مظهرها ومحتوياتها ، ثم قم بإلحاقها كطفل بالفقرة.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


