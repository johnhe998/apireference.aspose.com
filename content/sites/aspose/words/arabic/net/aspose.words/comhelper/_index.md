---
title: Class ComHelper
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ComHelper فصل. يوفر طرقًا لعملاء COM لتحميل مستند إلى Aspose.Words.
type: docs
weight: 210
url: /ar/net/aspose.words/comhelper/
---
## ComHelper class

يوفر طرقًا لعملاء COM لتحميل مستند إلى Aspose.Words.

```csharp
public class ComHelper
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [ComHelper](comhelper/)() | تهيئة مثيل جديد لهذه الفئة. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Open](../../aspose.words/comhelper/open/#open)(Stream) | يسمح بتحميل تطبيق COM[`Document`](../document/) من تيار . |
| [Open](../../aspose.words/comhelper/open/#open_1)(string) | يسمح لتطبيق COM بتحميل ملف[`Document`](../document/) من ملف . |
| [OpenIStream](../../aspose.words/comhelper/openistream/)(IStream) | يسمح لتطبيق COM بتحميل ملف[`Document`](../document/) من كائن IStream . |

### ملاحظات

استخدم ال`ComHelper` فئة لتحميل مستند من ملف أو دفق إلى [`Document`](../document/) كائن في تطبيق COM.

ال[`Document`](../document/)توفر الفئة مُنشئًا افتراضيًا لإنشاء document جديدًا وتوفر أيضًا مُنشِئات محملة بشكل زائد لتحميل مستند من ملف أو دفق . إذا كنت تستخدم Aspose.Words من تطبيق .NET ، فيمكنك استخدام كل[`Document`](../document/) المنشئات مباشرةً ، ولكن إذا كنت تستخدم Aspose.Words من تطبيق COM ، فقط الافتراضي[`Document`](../document/) منشئ متاح.

### أمثلة

```csharp
[VBScript]

Dim helper
Set helper = CreateObject("Aspose.Words.ComHelper")

Dim doc
Set doc = helper.Open(fileName)
```

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

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


