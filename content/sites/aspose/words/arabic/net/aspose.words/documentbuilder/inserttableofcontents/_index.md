---
title: DocumentBuilder.InsertTableOfContents
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. يقوم بإدراج حقل TOC جدول المحتويات في المستند.
type: docs
weight: 440
url: /ar/net/aspose.words/documentbuilder/inserttableofcontents/
---
## DocumentBuilder.InsertTableOfContents method

يقوم بإدراج حقل TOC (جدول المحتويات) في المستند.

```csharp
public Field InsertTableOfContents(string switches)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| switches | String | تبديل حقل TOC. |

### ملاحظات

تقوم هذه الطريقة بإدراج حقل TOC (جدول المحتويات) في المستند at الوضع الحالي.

يمكن إنشاء جدول محتويات في مستند Word بعدة طرق وتنسيقه باستخدام مجموعة متنوعة من الخيارات. يتم التحكم بالطريقة التي تم بها إنشاء الجدول و_ بواسطة Microsoft Word بواسطة مفاتيح التبديل الميدانية.

إن أسهل طريقة لتحديد رموز التبديل هي إدراج جدول محتويات وتكوينه في مستند Word باستخدام قائمة إدراج-&gt; مرجع-&gt; فهرس وجداول ، ثم تبديل عرض رموز الحقول لمشاهدة المحولات. يمكنك الضغط على Alt + F9 in Microsoft Word للتبديل بين تشغيل أو إيقاف تشغيل عرض رموز الحقول.

على سبيل المثال ، بعد إنشاء جدول محتويات ، يتم إدراج الحقل التالي في المستند: **{جدول المحتويات \ o "1-3" \ h \ z \ u}** . يمكنك نسخ **\ o "1-3" \ h \ z \ u** واستخدمها كمعامل مفاتيح.

لاحظ أن **InsertTableOfContents** سيقوم فقط بإدراج حقل جدول المحتويات ، ولكن لن يقوم في الواقع بإنشاء جدول المحتويات. تم إنشاء جدول المحتويات بواسطة Microsoft Word عند تحديث الحقل.

إذا أدخلت جدول محتويات باستخدام هذه الطريقة ثم فتحت file في Microsoft Word ، فلن ترى جدول المحتويات لأن جدول المحتويات field لم يتم تحديثه بعد.

في Microsoft Word ، لا يتم تحديث الحقول تلقائيًا عند فتح مستند ، ولكن يمكنك تحديث الحقول في مستند في أي وقت بالضغط على F9.

### أمثلة

يوضح كيفية إدراج جدول محتويات (TOC) في مستند باستخدام أنماط العناوين كمدخلات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل جدول محتويات للصفحة الأولى من المستند.
// تكوين الجدول لالتقاط فقرات بعناوين المستويات من 1 إلى 3.
// أيضًا ، قم بتعيين إدخالاتها لتكون ارتباطات تشعبية ستأخذنا
// إلى موقع العنوان عند النقر بزر الماوس الأيسر في Microsoft Word.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// ملء جدول المحتويات بإضافة فقرات بأنماط عناوين.
// كل عنوان بمستوى بين 1 و 3 سينشئ إدخالاً في الجدول.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// جدول المحتويات هو حقل من النوع يحتاج إلى تحديث لإظهار نتيجة محدثة.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### أنظر أيضا

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


