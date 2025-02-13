---
title: Interface INodeChangingCallback
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.INodeChangingCallback واجهه المستخدم. قم بتنفيذ هذه الواجهة إذا كنت تريد تلقي إعلامات عند إدراج العقد أو إزالتها في المستند.
type: docs
weight: 3000
url: /ar/net/aspose.words/inodechangingcallback/
---
## INodeChangingCallback interface

قم بتنفيذ هذه الواجهة إذا كنت تريد تلقي إعلامات عند إدراج العقد أو إزالتها في المستند.

```csharp
public interface INodeChangingCallback
```

## طُرق

| اسم | وصف |
| --- | --- |
| [NodeInserted](../../aspose.words/inodechangingcallback/nodeinserted/)(NodeChangingArgs) | يتم الاستدعاء عند إدراج عقدة تنتمي إلى هذا المستند في عقدة أخرى. |
| [NodeInserting](../../aspose.words/inodechangingcallback/nodeinserting/)(NodeChangingArgs) | تم الاستدعاء قبل أن توشك عقدة تنتمي إلى هذا المستند على أن يتم إدراجها في عقدة أخرى. |
| [NodeRemoved](../../aspose.words/inodechangingcallback/noderemoved/)(NodeChangingArgs) | يتم استدعائها عند إزالة عقدة تنتمي إلى هذا المستند من أصلها . |
| [NodeRemoving](../../aspose.words/inodechangingcallback/noderemoving/)(NodeChangingArgs) | تم الاستدعاء قبل أن تتم إزالة العقدة التي تنتمي إلى هذا المستند من المستند. |

### أمثلة

يوضح كيفية تخصيص تغيير العقدة مع رد الاتصال.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // تعيين استدعاء تغيير العقدة إلى التنفيذ المخصص ،
    // ثم قم بإضافة / إزالة العقد للحصول عليها لإنشاء سجل.
    HandleNodeChangingFontChanger callback = new HandleNodeChangingFontChanger();
    doc.NodeChangingCallback = callback;

    builder.Writeln("Hello world!");
    builder.Writeln("Hello again!");
    builder.InsertField(" HYPERLINK \"https://www.google.com/ \ "") ;
    builder.InsertShape(ShapeType.Rectangle, 300, 300);

    doc.Range.Fields[0].Remove();

    Console.WriteLine(callback.GetLog());

/// <summary>
/// يسجل تاريخ ووقت كل إدخال وإزالة عقدة.
/// يعين اسم / حجم خط مخصص لمحتويات نص عقد التشغيل.
/// </summary>
public class HandleNodeChangingFontChanger : INodeChangingCallback
{
    void INodeChangingCallback.NodeInserted(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash:\t{args.Node.GetHashCode()}");

        if (args.Node.NodeType == NodeType.Run)
        {
            Aspose.Words.Font font = ((Run) args.Node).Font;
            mLog.Append($"\tFont:\tChanged from \"{font.Name}\" {font.Size}pt");

            font.Size = 24;
            font.Name = "Arial";

            mLog.AppendLine($" to \"{font.Name}\" {font.Size}pt");
            mLog.AppendLine($"\tContents:\n\t\t\"{args.Node.GetText()}\"");
        }
    }

    void INodeChangingCallback.NodeInserting(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode insertion:");
    }

    void INodeChangingCallback.NodeRemoved(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash code:\t{args.Node.GetHashCode()}");
    }

    void INodeChangingCallback.NodeRemoving(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode removal:");
    }

    public string GetLog()
    {
        return mLog.ToString();
    }

    private readonly StringBuilder mLog = new StringBuilder();
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


