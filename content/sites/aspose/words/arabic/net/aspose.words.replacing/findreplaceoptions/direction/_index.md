---
title: FindReplaceOptions.Direction
second_title: Aspose.Words لمراجع .NET API
description: FindReplaceOptions ملكية. يحدد اتجاه الاستبدال. القيمة الافتراضية هيForward .
type: docs
weight: 40
url: /ar/net/aspose.words.replacing/findreplaceoptions/direction/
---
## FindReplaceOptions.Direction property

يحدد اتجاه الاستبدال. القيمة الافتراضية هيForward .

```csharp
public FindReplaceDirection Direction { get; set; }
```

### أمثلة

يوضح كيفية تحديد الاتجاه الذي تعبر فيه عملية البحث والاستبدال المستند.

```csharp
public void Direction(FindReplaceDirection findReplaceDirection)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // أدخل ثلاثة عمليات تشغيل يمكننا البحث عنها باستخدام نمط regex.
    // ضع واحدة من تلك التي تعمل داخل مربع نص.
    builder.Writeln("Match 1.");
    builder.Writeln("Match 2.");
    builder.Writeln("Match 3.");
    builder.Writeln("Match 4.");

    // يمكننا استخدام كائن "FindReplaceOptions" لتعديل عملية البحث والاستبدال.
    FindReplaceOptions options = new FindReplaceOptions();

    // تعيين رد اتصال مخصص لخاصية "ReplacingCallback".
    TextReplacementRecorder callback = new TextReplacementRecorder();
    options.ReplacingCallback = callback;

    // اضبط خاصية "الاتجاه" على "FindReplaceDirection.Backward" للحصول على البحث والاستبدال
    // لتبدأ من نهاية النطاق ، وتعود إلى البداية.
    // اضبط خاصية "الاتجاه" على "FindReplaceDirection.Backward" للحصول على البحث والاستبدال
    // لتبدأ من بداية النطاق ، وتنتقل إلى النهاية.
    options.Direction = findReplaceDirection;

    doc.Range.Replace(new Regex(@"Match \d*"), "Replacement", options);

    Assert.AreEqual("Replacement.\r" +
                    "Replacement.\r" +
                    "Replacement.\r" +
                    "Replacement.", doc.GetText().Trim());

    switch (findReplaceDirection)
    {
        case FindReplaceDirection.Forward:
            Assert.AreEqual(new[] { "Match 1", "Match 2", "Match 3", "Match 4" }, callback.Matches);
            break;
        case FindReplaceDirection.Backward:
            Assert.AreEqual(new[] { "Match 4", "Match 3", "Match 2", "Match 1" }, callback.Matches);
            break;
    }
}

/// <summary>
/// يسجل جميع التطابقات التي تحدث أثناء عملية البحث والاستبدال بالترتيب الذي تحدث فيه.
/// </summary>
private class TextReplacementRecorder : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs e)
    {
        Matches.Add(e.Match.Value);
        return ReplaceAction.Replace;
    }

    public List<string> Matches { get; } = new List<string>();
}
```

### أنظر أيضا

* enum [FindReplaceDirection](../../findreplacedirection/)
* class [FindReplaceOptions](../)
* مساحة الاسم [Aspose.Words.Replacing](../../findreplaceoptions/)
* المجسم [Aspose.Words](../../../)


