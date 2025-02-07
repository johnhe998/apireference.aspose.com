---
title: DocumentBuilder.InsertHyperlink
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. إدراج ارتباط تشعبي في المستند.
type: docs
weight: 340
url: /ar/net/aspose.words/documentbuilder/inserthyperlink/
---
## DocumentBuilder.InsertHyperlink method

إدراج ارتباط تشعبي في المستند.

```csharp
public Field InsertHyperlink(string displayText, string urlOrBookmark, bool isBookmark)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| displayText | String | سيتم عرض نص الارتباط في المستند. |
| urlOrBookmark | String | وجهة الارتباط. يمكن أن يكون عنوان url أو اسم إشارة مرجعية داخل المستند . تضيف هذه الطريقة دائمًا فاصلة عليا في بداية عنوان url ونهايته. |
| isBookmark | Boolean | صواب إذا كانت المعلمة السابقة هي اسم إشارة مرجعية داخل المستند ؛ false هي المعلمة السابقة هي عنوان URL. |

### قيمة الإرجاع

أ[`Field`](../../../aspose.words.fields/field/) كائن يمثل الحقل المدرج.

### ملاحظات

لاحظ أنك تحتاج إلى تحديد تنسيق الخط لنص عرض الارتباط التشعبي بشكل صريح_ باستخدام امتداد[`Font`](../font/) منشأه.

تستدعي هذه الطرق داخليًا[`InsertField`](../insertfield/) لإدراج حقل HYPERLINK MS Word في المستند.

### أمثلة

يوضح كيفية إدراج ارتباط تشعبي يشير إلى إشارة مرجعية محلية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("Bookmark1");
builder.Write("Bookmarked text. ");
builder.EndBookmark("Bookmark1");
builder.Writeln("Text outside of the bookmark.");

// أدخل حقل HYPERLINK الذي يرتبط بالإشارة المرجعية. يمكننا تمرير مفاتيح المجال
// إلى طريقة "InsertHyperlink" كجزء من الوسيطة التي تحتوي على اسم الإشارة المرجعية المشار إليها.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Link to Bookmark1", @"Bookmark1"" \o ""Hyperlink Tip", true);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlinkToLocalBookmark.docx");
```

يوضح كيفية إدراج حقل ارتباط تشعبي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// أدخل ارتباطًا تشعبيًا وقم بتأكيده بتنسيق مخصص.
// سيكون الارتباط التشعبي عبارة عن نص قابل للنقر عليه والذي سينقلنا إلى الموقع المحدد في عنوان URL.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com "، خطأ) ;
builder.Font.ClearFormatting();
builder.Writeln(".");

// Ctrl + النقر على الرابط الأيسر في النص في Microsoft Word سينقلنا إلى عنوان URL عبر نافذة متصفح ويب جديدة.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

يوضح كيفية استخدام مكدس التنسيق الخاص بمنشئ المستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إعداد تنسيق الخط ، ثم اكتب النص الذي يسبق الارتباط التشعبي.
builder.Font.Name = "Arial";
builder.Font.Size = 24;
builder.Write("To visit Google, hold Ctrl and click ");

// احتفظ بتكوين التنسيق الحالي الخاص بنا على المكدس.
builder.PushFont();

// قم بتعديل التنسيق الحالي للمنشئ من خلال تطبيق نمط جديد.
builder.Font.StyleIdentifier = StyleIdentifier.Hyperlink;
builder.InsertHyperlink("here", "http://www.google.com "، خطأ) ;

Assert.AreEqual(Color.Blue.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.Single, builder.Font.Underline);

// استعادة تنسيق الخط الذي حفظناه سابقًا وإزالة العنصر من المكدس.
builder.PopFont();

Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.None, builder.Font.Underline);

builder.Write(". We hope you enjoyed the example.");

doc.Save(ArtifactsDir + "DocumentBuilder.PushPopFont.docx");
```

### أنظر أيضا

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


