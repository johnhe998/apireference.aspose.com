---
title: FieldRef.NumberSeparator
second_title: Aspose.Words لمراجع .NET API
description: FieldRef ملكية. الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل أرقام التسلسل وأرقام الصفحات.
type: docs
weight: 90
url: /ar/net/aspose.words.fields/fieldref/numberseparator/
---
## FieldRef.NumberSeparator property

الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل أرقام التسلسل وأرقام الصفحات.

```csharp
public string NumberSeparator { get; set; }
```

### أمثلة

يوضح كيفية إدراج حقول REF للإشارة إلى الإشارات المرجعية.

```csharp
public void FieldRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #1");
    builder.Write("Text that will appear in REF field");
    builder.InsertFootnote(FootnoteType.Footnote, "MyBookmark footnote #2");
    builder.EndBookmark("MyBookmark");
    builder.MoveToDocumentStart();

    // سنقوم بتطبيق تنسيق قائمة مخصص ، حيث يشير مقدار أقواس الزاوية إلى مستوى القائمة الذي نحن عليه حاليًا.
    builder.ListFormat.ApplyNumberDefault();
    builder.ListFormat.ListLevel.NumberFormat = "> \x0000";

    // أدخل حقل REF يحتوي على النص داخل الإشارة المرجعية الخاصة بنا ، ويعمل كارتباط تشعبي ، ويستنسخ الحواشي السفلية للإشارة المرجعية.
    FieldRef field = InsertFieldRef(builder, "MyBookmark", "", "\n");
    field.IncludeNoteOrComment = true;
    field.InsertHyperlink = true;

    Assert.AreEqual(" REF  MyBookmark \\f \\h", field.GetFieldCode());

    // أدخل حقل REF ، واعرض ما إذا كانت الإشارة المرجعية المرجعية أعلى أو تحته.
    field = InsertFieldRef(builder, "MyBookmark", "The referenced paragraph is ", " this field.\n");
    field.InsertRelativePosition = true;

    Assert.AreEqual(" REF  MyBookmark \\p", field.GetFieldCode());

    // عرض رقم قائمة الإشارة المرجعية كما تظهر في المستند.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number is ", "\n");
    field.InsertParagraphNumber = true;

    Assert.AreEqual(" REF  MyBookmark \\n", field.GetFieldCode());

    // عرض رقم قائمة الإشارة ، ولكن مع حذف أحرف غير محددة ، مثل أقواس الزاوية.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's paragraph number, non-delimiters suppressed, is ", "\n");
    field.InsertParagraphNumber = true;
    field.SuppressNonDelimiters = true;

    Assert.AreEqual(" REF  MyBookmark \\n \\t", field.GetFieldCode());

    // تحرك لأسفل مستوى قائمة واحد.
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">> \x0001";

    // عرض رقم قائمة الإشارة المرجعية وأرقام جميع مستويات القائمة أعلاه.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's full context paragraph number is ", "\n");
    field.InsertParagraphNumberInFullContext = true;

    Assert.AreEqual(" REF  MyBookmark \\w", field.GetFieldCode());

    builder.InsertBreak(BreakType.PageBreak);

    // عرض أرقام مستوى القائمة بين حقل REF هذا ، والإشارة المرجعية التي تشير إليها.
    field = InsertFieldRef(builder, "MyBookmark", "The bookmark's relative paragraph number is ", "\n");
    field.InsertParagraphNumberInRelativeContext = true;

    Assert.AreEqual(" REF  MyBookmark \\r", field.GetFieldCode());

    // في نهاية المستند ، ستظهر الإشارة المرجعية كعنصر قائمة هنا.
    builder.Writeln("List level above bookmark");
    builder.ListFormat.ListLevelNumber++;
    builder.ListFormat.ListLevel.NumberFormat = ">>> \x0002";

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.REF.docx");

/// <summary>
/// احصل على مُنشئ المستندات لإدراج حقل REF ، والإشارة إلى إشارة مرجعية معه ، وإضافة نص قبله وبعده.
/// </summary>
private static FieldRef InsertFieldRef(DocumentBuilder builder, string bookmarkName, string textBefore, string textAfter)
{
    builder.Write(textBefore);
    FieldRef field = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    field.BookmarkName = bookmarkName;
    builder.Write(textAfter);
    return field;
}
```

### أنظر أيضا

* class [FieldRef](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldref/)
* المجسم [Aspose.Words](../../../)


