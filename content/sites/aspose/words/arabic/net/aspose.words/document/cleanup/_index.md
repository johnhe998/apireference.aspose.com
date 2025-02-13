---
title: Document.Cleanup
second_title: Aspose.Words لمراجع .NET API
description: Document طريقة. ينظف الأنماط والقوائم غير المستخدمة من المستند.
type: docs
weight: 520
url: /ar/net/aspose.words/document/cleanup/
---
## Cleanup() {#cleanup}

ينظف الأنماط والقوائم غير المستخدمة من المستند.

```csharp
public void Cleanup()
```

### أمثلة

يوضح كيفية إزالة الأنماط المخصصة غير المستخدمة من مستند.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// بالاقتران مع الأنماط المضمنة ، يحتوي المستند الآن على ثمانية أنماط.
// يعد النمط المخصص "مستخدمًا" أثناء تطبيقه على جزء من المستند ،
// مما يعني أن الأنماط الأربعة التي أضفناها غير مستخدمة حاليًا.
Assert.AreEqual(8, doc.Styles.Count);

// تطبيق نمط حرف مخصص ، ثم نمط قائمة مخصص. سيؤدي القيام بذلك إلى وضع علامة على الأنماط على أنها "مستعملة".
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

doc.Cleanup();

Assert.AreEqual(6, doc.Styles.Count);

// إزالة كل عقدة يتم تطبيق نمط مخصص عليها لوضع علامة عليها على أنها "غير مستخدمة" مرة أخرى.
// قم بتشغيل طريقة التنظيف مرة أخرى لإزالتها.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup();

Assert.AreEqual(4, doc.Styles.Count);
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)

---

## Cleanup(CleanupOptions) {#cleanup_1}

ينظف الأنماط والقوائم غير المستخدمة من المستند حسب المعطى[`CleanupOptions`](../../cleanupoptions/) .

```csharp
public void Cleanup(CleanupOptions options)
```

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

* class [CleanupOptions](../../cleanupoptions/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


