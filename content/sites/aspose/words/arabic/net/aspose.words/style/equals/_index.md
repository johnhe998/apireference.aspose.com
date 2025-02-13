---
title: Style.Equals
second_title: Aspose.Words لمراجع .NET API
description: Style طريقة. مقارنة بالنمط المحدد . تتم مقارنة الأنماط للأنماط المضمنة فقط . لا يتم تضمين افتراضيات الأنماط في المقارنة. تتم مقارنة النمط الأساسي والنمط المرتبط ونمط الفقرة التالي بشكل متكرر.
type: docs
weight: 170
url: /ar/net/aspose.words/style/equals/
---
## Style.Equals method

مقارنة بالنمط المحدد . تتم مقارنة الأنماط للأنماط المضمنة فقط . لا يتم تضمين افتراضيات الأنماط في المقارنة. تتم مقارنة النمط الأساسي والنمط المرتبط ونمط الفقرة التالي بشكل متكرر.

```csharp
public bool Equals(Style style)
```

### أمثلة

يوضح كيفية استخدام الأسماء المستعارة للأنماط.

```csharp
Document doc = new Document(MyDir + "Style with alias.docx");

// يحتوي هذا المستند على نمط يسمى "MyStyle ، MyStyle Alias 1 ، MyStyle Alias 2".
// إذا كان اسم النمط يحتوي على قيم متعددة مفصولة بفاصلات ، فإن كل عبارة عبارة عن اسم مستعار منفصل.
Style style = doc.Styles["MyStyle"];
Assert.AreEqual(new [] { "MyStyle Alias 1", "MyStyle Alias 2" }, style.Aliases);
Assert.AreEqual("Title", style.BaseStyleName);
Assert.AreEqual("MyStyle Char", style.LinkedStyleName);

// يمكننا الإشارة إلى نمط باستخدام اسمه المستعار ، بالإضافة إلى اسمه.
Assert.AreEqual(doc.Styles["MyStyle Alias 1"], doc.Styles["MyStyle Alias 2"]);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 2"];
builder.Write("Hello again!");

Assert.AreEqual(doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.Style, 
    doc.FirstSection.Body.Paragraphs[1].ParagraphFormat.Style);
```

### أنظر أيضا

* class [Style](../)
* مساحة الاسم [Aspose.Words](../../style/)
* المجسم [Aspose.Words](../../../)


