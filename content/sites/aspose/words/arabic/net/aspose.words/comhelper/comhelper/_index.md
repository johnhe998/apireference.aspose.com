---
title: ComHelper.ComHelper
second_title: Aspose.Words لمراجع .NET API
description: ComHelper البناء. تهيئة مثيل جديد لهذه الفئة.
type: docs
weight: 10
url: /ar/net/aspose.words/comhelper/comhelper/
---
## ComHelper constructor

تهيئة مثيل جديد لهذه الفئة.

```csharp
public ComHelper()
```

### أمثلة

يوضح كيفية فتح المستندات باستخدام فئة ComHelper.

```csharp
// تسمح لنا فئة ComHelper بتحميل المستندات من داخل عملاء COM.
ComHelper comHelper = new ComHelper();

// 1 - استخدام اسم ملف نظام محلي:
Document doc = comHelper.Open(MyDir + "Document.docx");

Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// 2 - من تيار:
using (FileStream stream = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    doc = comHelper.Open(stream);

    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());
}
```

### أنظر أيضا

* class [ComHelper](../)
* مساحة الاسم [Aspose.Words](../../comhelper/)
* المجسم [Aspose.Words](../../../)


