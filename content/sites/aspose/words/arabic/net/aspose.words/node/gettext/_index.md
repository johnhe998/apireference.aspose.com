---
title: Node.GetText
second_title: Aspose.Words لمراجع .NET API
description: Node طريقة. يحصل على نص هذه العقدة وجميع توابعها.
type: docs
weight: 120
url: /ar/net/aspose.words/node/gettext/
---
## Node.GetText method

يحصل على نص هذه العقدة وجميع توابعها.

```csharp
public virtual string GetText()
```

### ملاحظات

تتضمن السلسلة التي تم إرجاعها كل عناصر التحكم والأحرف الخاصة كما هو موضح في[`ControlChar`](../../controlchar/).

### أمثلة

يوضح كيفية استخدام أحرف التحكم.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل فقرات مع نص باستخدام DocumentBuilder.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

// تحويل المستند إلى نموذج نصي يكشف عن التحكم في الأحرف
// تمثل بعض العناصر الهيكلية للمستند ، مثل فواصل الصفحات.
Assert.AreEqual($"Hello world!{ControlChar.Cr}" +
                $"Hello again!{ControlChar.Cr}" +
                ControlChar.PageBreak, doc.GetText());

// عند تحويل مستند إلى شكل سلسلة ،
// يمكننا حذف بعض أحرف التحكم باستخدام طريقة Trim.
Assert.AreEqual($"Hello world!{ControlChar.Cr}" +
                "Hello again!", doc.GetText().Trim());
```

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

* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


