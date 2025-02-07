---
title: TxtSaveOptions.SimplifyListLabels
second_title: Aspose.Words لمراجع .NET API
description: TxtSaveOptions ملكية. يحدد ما إذا كان يجب على البرنامج تبسيط تسميات القائمة في حالة تنسيق الملصق المعقد الذي لا يتم تمثيله بشكل كافٍ بنص عادي.
type: docs
weight: 70
url: /ar/net/aspose.words.saving/txtsaveoptions/simplifylistlabels/
---
## TxtSaveOptions.SimplifyListLabels property

يحدد ما إذا كان يجب على البرنامج تبسيط تسميات القائمة في حالة تنسيق الملصق المعقد الذي لا يتم تمثيله بشكل كافٍ بنص عادي.

إذا تم التعيين على **حقيقي** ، تتم كتابة تسميات القائمة المرقمة بتنسيق رقمي بسيط وتسميات قائمة مفصلة كأحرف ASCII بسيطة. النظام الأساسي **خاطئة**.

```csharp
public bool SimplifyListLabels { get; set; }
```

### أمثلة

يوضح كيفية تغيير مظهر القوائم عند حفظ مستند إلى نص عادي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إنشاء قائمة نقطية بخمسة مستويات من المسافة البادئة.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent();
builder.Writeln("Item 3");
builder.ListFormat.ListIndent();
builder.Writeln("Item 4");
builder.ListFormat.ListIndent();
builder.Write("Item 5");

// قم بإنشاء كائن "TxtSaveOptions" ، والذي يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية حفظ المستند على نص عادي.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// اضبط خاصية "SimplifyListLabels" على "true" لتحويل بعض القوائم
// الرموز إلى أحرف ASCII أبسط ، مثل "*" و "o" و "+" و ">" وما إلى ذلك.
// اضبط خاصية "SimplifyListLabels" على "false" للحفاظ على أكبر عدد ممكن من رموز القائمة الأصلية.
txtSaveOptions.SimplifyListLabels = simplifyListLabels;

doc.Save(ArtifactsDir + "TxtSaveOptions.SimplifyListLabels.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.SimplifyListLabels.txt");

if (simplifyListLabels)
    Assert.AreEqual("* Item 1\r\n" +
                    "  > Item 2\r\n" +
                    "    + Item 3\r\n" +
                    "      - Item 4\r\n" +
                    "        o Item 5\r\n", docText);
else
    Assert.AreEqual("· Item 1\r\n" +
                    "o Item 2\r\n" +
                    "§ Item 3\r\n" +
                    "· Item 4\r\n" +
                    "o Item 5\r\n", docText);
```

### أنظر أيضا

* class [TxtSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../txtsaveoptions/)
* المجسم [Aspose.Words](../../../)


