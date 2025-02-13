---
title: Class CleanupOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.CleanupOptions فصل. يسمح بتحديد خيارات لتنظيف المستندات .
type: docs
weight: 200
url: /ar/net/aspose.words/cleanupoptions/
---
## CleanupOptions class

يسمح بتحديد خيارات لتنظيف المستندات .

```csharp
public class CleanupOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [CleanupOptions](cleanupoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [DuplicateStyle](../../aspose.words/cleanupoptions/duplicatestyle/) { get; set; } | يحصل / يحدد علامة تشير إلى ما إذا كان يجب إزالة الأنماط المكررة من المستند. القيمة الافتراضية هي **خاطئة** . |
| [UnusedBuiltinStyles](../../aspose.words/cleanupoptions/unusedbuiltinstyles/) { get; set; } | تحديد ذلك غير المستخدم[`BuiltIn`](../style/builtin/) يجب إزالة الأنماط من المستند. |
| [UnusedLists](../../aspose.words/cleanupoptions/unusedlists/) { get; set; } | يحدد ما إذا كان يجب إزالة تعريفات القائمة والقائمة غير المستخدمة من المستند. القيمة الافتراضية هي **حقيقي** . |
| [UnusedStyles](../../aspose.words/cleanupoptions/unusedstyles/) { get; set; } | يحدد ما إذا كان يجب إزالة الأنماط غير المستخدمة من المستند. القيمة الافتراضية هي **حقيقي** . |

### أمثلة

يوضح كيفية إزالة جميع الأنماط المخصصة غير المستخدمة من مستند.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// بالاقتران مع الأنماط المضمنة ، يحتوي المستند الآن على ثمانية أنماط.
// يتم تمييز النمط المخصص على أنه "مستخدم" أثناء وجود أي نص داخل المستند
// منسق بهذا النمط. هذا يعني أن الأنماط الأربعة التي أضفناها غير مستخدمة حاليًا.
Assert.AreEqual(8, doc.Styles.Count);

// تطبيق نمط حرف مخصص ، ثم نمط قائمة مخصص. سيؤدي القيام بذلك إلى تمييزها على أنها "مستخدمة".
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

// الآن ، يوجد نمط حرف واحد غير مستخدم ونمط قائمة واحد غير مستخدم.
// يمكن لطريقة Cleanup () ، عند تكوينها باستخدام كائن CleanupOptions ، استهداف الأنماط غير المستخدمة وإزالتها.
CleanupOptions cleanupOptions = new CleanupOptions
{
    UnusedLists = true, UnusedStyles = true, UnusedBuiltinStyles = true
};

doc.Cleanup(cleanupOptions);

Assert.AreEqual(4, doc.Styles.Count);

// إزالة كل عقدة يتم تطبيق نمط مخصص عليها لوضع علامة عليها على أنها "غير مستخدمة" مرة أخرى. 
// أعد تشغيل طريقة التنظيف لإزالتها.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup(cleanupOptions);

Assert.AreEqual(2, doc.Styles.Count);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


