---
title: ListLabel.LabelValue
second_title: Aspose.Words لمراجع .NET API
description: ListLabel ملكية. الحصول على قيمة رقمية لهذا التصنيف.
type: docs
weight: 30
url: /ar/net/aspose.words.lists/listlabel/labelvalue/
---
## ListLabel.LabelValue property

الحصول على قيمة رقمية لهذا التصنيف.

```csharp
public int LabelValue { get; }
```

### ملاحظات

استخدم ملف[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) طريقة لتحديث قيمة هذه الخاصية .

### أمثلة

يوضح كيفية استخراج تسميات القائمة لكل الفقرات التي تمثل عناصر قائمة.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// ابحث عما إذا كان لدينا قائمة الفقرات. في وثيقتنا ، تستخدم قائمتنا أرقامًا عربية بسيطة ،
// التي تبدأ عند الثالثة وتنتهي عند السادسة.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // هذا هو النص الذي نحصل عليه عند إخراج هذه العقدة إلى تنسيق نصي.
    // سيحذف إخراج النص هذا تسميات القائمة. تقليم أي أحرف تنسيق الفقرة. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // هذا يحصل على موضع الفقرة في المستوى الحالي من القائمة. إذا كانت لدينا قائمة بمستويات متعددة ،
    // سيخبرنا هذا بالموقع الذي وصلت إليه على هذا المستوى.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // اجمعها معًا لتضمين تسمية القائمة مع النص في الإخراج.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### أنظر أيضا

* class [ListLabel](../)
* مساحة الاسم [Aspose.Words.Lists](../../listlabel/)
* المجسم [Aspose.Words](../../../)


