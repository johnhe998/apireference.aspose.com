---
title: تعيين مجلدات الخطوط ذات الأولوية
linktitle: تعيين مجلدات الخطوط ذات الأولوية
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل خطوة بخطوة لإعداد مجلدات الخطوط ذات الأولوية عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folders-with-priority/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلدات الخطوط ذات الأولوية عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد مجلدات خطوط متعددة ذات أولوية بحث مخصصة عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تعيين مجلدات الخطوط ذات الأولوية
 ثم يمكنك ضبط مجلدات الخطوط ذات الأولوية باستخدام امتداد`FontSettings` الطبقة و`SetFontsSources()`طريقة. يمكنك تحديد مصادر خطوط متعددة باستخدام مثيلات`SystemFontSource` و`FolderFontSource`. في هذا المثال ، حددنا مصدرين للخطوط: المصدر الافتراضي لخطوط النظام ومجلد الخط المخصص بأولوية 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## الخطوة 3: قم بتحميل المستند للعرض
 يمكنك الآن تحميل المستند لتقديمه باستخدام امتداد`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 4: احفظ المستند المقدم
 أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### عينة من التعليمات البرمجية المصدر لـ Set Fonts Folders With Priority باستخدام Aspose.Words for .NET 
```csharp
//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مجلدات الخطوط ذات الأولوية عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تحديد مجلدات خطوط متعددة ذات أولوية بحث مخصصة عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في مصادر الخطوط المستخدمة عند تقديم مستنداتك لاحتياجاتك الخاصة وتخصيصها.

### التعليمات

#### س: كيف يمكنني تعيين مجلدات الخطوط ذات الأولوية في Aspose.Words؟

 ج: لتعيين مجلدات الخطوط ذات الأولوية في Aspose.Words ، يمكنك استخدام`SetFontsFoldersWithPriority` طريقة`Fonts` class عن طريق تحديد مواقع مجلدات الخطوط وترتيب أولوياتها.

#### س: ماذا يحدث إذا كان الخط موجودًا في عدة مجلدات ذات أولوية مختلفة؟

ج: إذا كان الخط موجودًا في مجلدات متعددة ذات أولوية مختلفة ، فإن Aspose.Words ستستخدم النسخة من المجلد ذات الأولوية القصوى عند معالجة المستندات.

#### س: هل يمكنني تحديد مجلدات خطوط متعددة لها نفس الأولوية في Aspose.Words؟

ج: نعم ، يمكنك تحديد مجلدات خطوط متعددة لها نفس الأولوية في Aspose.Words. Aspose. Words ستعتبرهم جميعًا ذات أولوية متساوية عند البحث عن الخطوط في مستنداتك.

#### س: كيف يمكنني التحقق من مجلدات الخطوط المحددة بالأولوية في Aspose.Words؟

 ج: للتحقق من مجلدات الخطوط المحددة مع الأولوية في Aspose.Words ، يمكنك استخدام`GetFolders` طريقة`Fonts` فئة للحصول على قائمة بمجلدات الخطوط المكونة بما في ذلك ترتيب أولوياتها.

#### س: ما فائدة تعيين مجلدات الخطوط ذات الأولوية في Aspose.Words؟

ج: تعيين مجلدات الخطوط ذات الأولوية في Aspose.Words يسمح لك بالتحكم في ترتيب البحث للخطوط في مستندات Word الخاصة بك. يساعدك هذا في التأكد من استخدام الخطوط التي تريدها وتجنب مشكلات استبدال الخطوط غير المرغوب فيها.