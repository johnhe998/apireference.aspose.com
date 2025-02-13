---
title: Class AsposeWordsPrintDocument
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Rendering.AsposeWordsPrintDocument فصل. يوفر تطبيقًا افتراضيًا لطباعة ملفDocument within إطار عمل طباعة .NET .
type: docs
weight: 4280
url: /ar/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

يوفر تطبيقًا افتراضيًا لطباعة ملف[`Document`](../../aspose.words/document/) within إطار عمل طباعة .NET .

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | تهيئة مثيل جديد لهذه الفئة. |

## طُرق

| اسم | وصف |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | يقرأ ويخزن بعض حقولPrinterSettings لتقليل وقت الطباعة. |

### ملاحظات

`AsposeWordsPrintDocument` يتجاوزPrintEventArgs) لطباعة نطاق الصفحات المحدد فيPrinterSettings.

يمكن أن يتكون مستند Word الفردي من أقسام متعددة تحدد الصفحات بأحجام مختلفة واتجاه وأدراج ورق.`AsposeWordsPrintDocument` تجاوزات QueryPageSettingsEventArgs) لتحديد حجم الورق والتوجيه ومصدر الورق بشكل صحيح عند طباعة مستند Word.

يقوم Microsoft Word بتخزين قيم خاصة بالطابعة لأدراج الورق في مستند Word ، وبالتالي ، فإن الطباعة على نفس طراز الطابعة فقط مثل التي تم تحديدها عندما حدد المستخدم علبة الورق ستؤدي إلى الطباعة من الأدراج الصحيحة. إذا قمت بطباعة مستند على طابعة مختلفة ، فعلى الأرجح سيتم استخدام درج الورق الافتراضي ، وليس الأدراج المحددة في المستند.

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Rendering](../../aspose.words.rendering/)
* المجسم [Aspose.Words](../../)


