---
title: Revision.ParentStyle
second_title: Aspose.Words لمراجع .NET API
description: Revision ملكية. الحصول على النمط الأصل المباشر المالك لهذه المراجعة . ستعمل هذه الخاصية فقط معStyleDefinitionChange نوع المراجعة .
type: docs
weight: 50
url: /ar/net/aspose.words/revision/parentstyle/
---
## Revision.ParentStyle property

الحصول على النمط الأصل المباشر (المالك) لهذه المراجعة . ستعمل هذه الخاصية فقط معStyleDefinitionChange نوع المراجعة .

```csharp
public Style ParentStyle { get; }
```

### ملاحظات

إذا كانت هذه المراجعة تتعلق بالتغييرات في عقد المستند ، فاستخدم[`ParentNode`](../parentnode/) بدلاً من ذلك .

### أمثلة

يوضح كيفية العمل مع مجموعة المراجعات الخاصة بمستند.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
RevisionCollection revisions = doc.Revisions;

// تحتوي هذه المجموعة نفسها على مجموعة من مجموعات المراجعة.
// كل مجموعة عبارة عن سلسلة من المراجعات المتجاورة.
Console.WriteLine($"{revisions.Groups.Count} revision groups:");

// كرر عبر مجموعة المجموعات واطبع النص الذي تهم المراجعة.
using (IEnumerator<RevisionGroup> e = revisions.Groups.GetEnumerator())
{
    while (e.MoveNext())
    {
        Console.WriteLine($"\tGroup type \"{e.Current.RevisionType}\", " +
                          $"author: {e.Current.Author}, contents: [{e.Current.Text.Trim()}]");
    }
}

// كل عملية تشغيل تؤثر عليها مراجعة تحصل على كائن مراجعة مطابق.
// مجموعة المراجعات أكبر بكثير من النموذج المكثف الذي قمنا بطباعته أعلاه ،
// اعتمادًا على عدد عمليات التشغيل التي قمنا بتقسيم المستند إليها أثناء تحرير Microsoft Word.
Console.WriteLine($"\n{revisions.Count} revisions:");

using (IEnumerator<Revision> e = revisions.GetEnumerator())
{
    while (e.MoveNext())
    {
        // A StyleDefinitionChange يؤثر بشكل صارم على الأنماط وليس عقد المستند. هذا يعني "ParentStyle"
        // ستظل الخاصية قيد الاستخدام دائمًا ، بينما ستكون ParentNode خالية دائمًا.
        // نظرًا لأن جميع التغييرات الأخرى تؤثر على العقد ، فسيكون ParentNode قيد الاستخدام ، وسيكون ParentStyle فارغًا.
        if (e.Current.RevisionType == RevisionType.StyleDefinitionChange)
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, style: [{e.Current.ParentStyle.Name}]");
        }
        else
        {
            Console.WriteLine($"\tRevision type \"{e.Current.RevisionType}\", " +
                              $"author: {e.Current.Author}, contents: [{e.Current.ParentNode.GetText().Trim()}]");
        }
    }
}

// رفض جميع المراجعات عبر المجموعة ، مع إعادة المستند إلى شكله الأصلي.
revisions.RejectAll();

Assert.AreEqual(0, revisions.Count);
```

### أنظر أيضا

* class [Style](../../style/)
* class [Revision](../)
* مساحة الاسم [Aspose.Words](../../revision/)
* المجسم [Aspose.Words](../../../)


