---
title: MailMerge.MailMergeCallback
second_title: Aspose.Words لمراجع .NET API
description: MailMerge ملكية. يسمح بمعالجة أحداث معينة أثناء دمج البريد.
type: docs
weight: 40
url: /ar/net/aspose.words.mailmerging/mailmerge/mailmergecallback/
---
## MailMerge.MailMergeCallback property

يسمح بمعالجة أحداث معينة أثناء دمج البريد.

```csharp
public IMailMergeCallback MailMergeCallback { get; set; }
```

### أمثلة

يوضح كيفية تحديد منطق مخصص لمعالجة الأحداث أثناء دمج البريد.

```csharp
public void Callback()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // أدخل علامتي دمج مراسلات تشيران إلى عمودين في مصدر بيانات.
    builder.Write("{{FirstName}}");
    builder.Write("{{LastName}}");

    // قم بإنشاء مصدر بيانات يحتوي على عمود واحد فقط من الأعمدة التي تشير إليها علامات الدمج الخاصة بنا.
    DataTable table = new DataTable("Test");
    table.Columns.Add("FirstName");
    table.Rows.Add("John");
    table.Rows.Add("Jane");

    // تكوين دمج المراسلات لدينا لاستخدام علامات دمج المراسلات البديلة.
    doc.MailMerge.UseNonMergeFields = true;

    // بعد ذلك ، تأكد من أن دمج المراسلات سيحول العلامات ، مثل علامة "LastName" الخاصة بنا ،
    // في MERGEFIELDs في مستندات الدمج.
    doc.MailMerge.PreserveUnusedTags = false;

    MailMergeTagReplacementCounter counter = new MailMergeTagReplacementCounter();
    doc.MailMerge.MailMergeCallback = counter;
    doc.MailMerge.Execute(table);

    Assert.AreEqual(1, counter.TagsReplacedCount);
}

/// <summary>
/// تحسب عدد المرات التي استبدل فيها دمج المراسلات علامات دمج المراسلات التي لم يتمكن من تعبئتها بالبيانات بـ MERGEFIELDs.
/// </summary>
private class MailMergeTagReplacementCounter : IMailMergeCallback
{
    public void TagsReplaced()
    {
        TagsReplacedCount++;
    }

    public int TagsReplacedCount { get; private set; }
}
```

### أنظر أيضا

* interface [IMailMergeCallback](../../imailmergecallback/)
* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)


