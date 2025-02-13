---
title: Enum EditorType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.EditorType تعداد. يحدد مجموعة من الأسماء المستعارة المحتملة أو مجموعات التحرير التي يمكن استخدامها كأسماء مستعارة لتحديد ما إذا كان المستخدم الحالي مسموحًا له بتحرير نطاق واحد محدد بنطاق قابل للتحرير داخل مستند.
type: docs
weight: 1300
url: /ar/net/aspose.words/editortype/
---
## EditorType enumeration

يحدد مجموعة من الأسماء المستعارة المحتملة (أو مجموعات التحرير) التي يمكن استخدامها كأسماء مستعارة لتحديد ما إذا كان المستخدم الحالي مسموحًا له بتحرير نطاق واحد محدد بنطاق قابل للتحرير داخل مستند.

```csharp
public enum EditorType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Unspecified | `0` | يعني أنه لم يتم تحديد نوع المحرر. |
| Administrators | `1` | يحدد السماح للمستخدمين المرتبطين بمجموعة المسؤولين بتحرير نطاقات قابلة للتحرير باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Contributors | `2` | يحدد السماح للمستخدمين المرتبطين بمجموعة المساهمين بتحرير نطاقات قابلة للتحرير باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Current | `3` | يحدد أنه يجب السماح للمستخدمين المرتبطين بالمجموعة الحالية بتحرير النطاقات القابلة للتحرير باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Editors | `4` | يحدد السماح للمستخدمين المرتبطين بمجموعة المحررين بتحرير نطاقات قابلة للتحرير باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Everyone | `5` | يحدد أنه يجب السماح لجميع المستخدمين الذين يفتحون المستند بتحرير النطاقات القابلة للتحرير باستخدام هذا النوع من التحرير_ عند تمكين حماية المستند. |
| None | `6` | يحدد عدم السماح لأي من المستخدمين الذين يفتحون المستند بتحرير النطاقات القابلة للتحرير_ باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Owners | `7` | يحدد أنه يجب السماح للمستخدمين المرتبطين بمجموعة المالكين بتحرير النطاقات القابلة للتحرير باستخدام نوع التحرير هذا عند تمكين حماية المستند. |
| Default | `0` | نفسUnspecified . |

### أمثلة

يوضح كيفية تقييد حقوق التحرير للنطاقات القابلة للتحرير لمجموعة / مستخدم معين.

```csharp
public void Visitor()
{
    Document doc = new Document();
    doc.Protect(ProtectionType.ReadOnly, "MyPassword");

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world! Since we have set the document's protection level to read-only," +
                    " we cannot edit this paragraph without the password.");

    // عندما نكتب حماية المستندات ، تسمح لنا النطاقات القابلة للتحرير باختيار مناطق محددة يمكن للمستخدمين تحريرها.
    // هناك طريقتان متنافيتان لتضييق نطاق قائمة المحررين المسموح لهم.
    // 1 - حدد مستخدمًا:
    EditableRange editableRange = builder.StartEditableRange().EditableRange;
    editableRange.SingleUser = "john.doe@myoffice.com";
    builder.Writeln($"This paragraph is inside the first editable range, can only be edited by {editableRange.SingleUser}.");
    builder.EndEditableRange();

    Assert.AreEqual(EditorType.Unspecified, editableRange.EditorGroup);

    // 2 - حدد مجموعة يرتبط بها المستخدمون المسموح لهم بـ:
    editableRange = builder.StartEditableRange().EditableRange;
    editableRange.EditorGroup = EditorType.Administrators;
    builder.Writeln($"This paragraph is inside the first editable range, can only be edited by {editableRange.EditorGroup}.");
    builder.EndEditableRange();

    Assert.AreEqual(string.Empty, editableRange.SingleUser);

    builder.Writeln("This paragraph is outside the editable range, and cannot be edited by anybody.");

    // طباعة تفاصيل ومحتويات كل نطاق قابل للتحرير في المستند.
    EditableRangePrinter editableRangePrinter = new EditableRangePrinter();

    doc.Accept(editableRangePrinter);

    Console.WriteLine(editableRangePrinter.ToText());
}

/// <summary>
/// يجمع خصائص ومحتويات النطاقات القابلة للتحرير التي تمت زيارتها في سلسلة.
/// </summary>
public class EditableRangePrinter : DocumentVisitor
{
    public EditableRangePrinter()
    {
        mBuilder = new StringBuilder();
    }

    public string ToText()
    {
        return mBuilder.ToString();
    }

    public void Reset()
    {
        mBuilder.Clear();
        mInsideEditableRange = false;
    }

    /// <summary>
    /// يتم الاستدعاء عند مواجهة عقدة EditableRangeStart في المستند.
    /// </summary>
    public override VisitorAction VisitEditableRangeStart(EditableRangeStart editableRangeStart)
    {
        mBuilder.AppendLine(" -- Editable range found! -- ");
        mBuilder.AppendLine("\tID:\t\t" + editableRangeStart.Id);
        if (editableRangeStart.EditableRange.SingleUser == string.Empty)
            mBuilder.AppendLine("\tGroup:\t" + editableRangeStart.EditableRange.EditorGroup);
        else
            mBuilder.AppendLine("\tUser:\t" + editableRangeStart.EditableRange.SingleUser);
        mBuilder.AppendLine("\tContents:");

        mInsideEditableRange = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عند مواجهة عقدة EditableRangeEnd في المستند.
    /// </summary>
    public override VisitorAction VisitEditableRangeEnd(EditableRangeEnd editableRangeEnd)
    {
        mBuilder.AppendLine(" -- End of editable range --\n");

        mInsideEditableRange = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عند مواجهة عقدة تشغيل في المستند. يسجل هذا الزائر فقط عمليات التشغيل الموجودة داخل نطاقات قابلة للتحرير.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        if (mInsideEditableRange) mBuilder.AppendLine("\t\"" + run.Text + "\"");

        return VisitorAction.Continue;
    }

    private bool mInsideEditableRange;
    private readonly StringBuilder mBuilder;
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


