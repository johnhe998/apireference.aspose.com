---
title: NodeList.GetEnumerator
second_title: Aspose.Words لمراجع .NET API
description: NodeList طريقة. يوفر تكرارًا بسيطًا لنمط foreach عبر مجموعة العقد.
type: docs
weight: 30
url: /ar/net/aspose.words/nodelist/getenumerator/
---
## NodeList.GetEnumerator method

يوفر تكرارًا بسيطًا لنمط "foreach" عبر مجموعة العقد.

```csharp
public IEnumerator<Node> GetEnumerator()
```

### قيمة الإرجاع

مبسط IEnumerator.

### أمثلة

يوضح كيفية تحديد عقد معينة باستخدام تعبير XPath.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// هذا التعبير سوف يستخرج جميع عقد الفقرة ،
// التي تنحدر من أي عقدة جدول في المستند.
NodeList nodeList = doc.SelectNodes("// جدول // فقرة ") ;

// كرر من خلال القائمة باستخدام العداد واطبع محتويات كل فقرة في كل خلية من خلايا الجدول.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// سيحدد هذا التعبير أي فقرات تكون فرعية مباشرة لأي عقدة أساسية في المستند.
nodeList = doc.SelectNodes("// نص / فقرة ") ;

// يمكننا التعامل مع القائمة كمصفوفة.
Assert.AreEqual(4, nodeList.ToArray().Length);

// استخدم SelectSingleNode لتحديد النتيجة الأولى لنفس التعبير على النحو الوارد أعلاه.
Node node = doc.SelectSingleNode("// نص / فقرة ") ;

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### أنظر أيضا

* class [Node](../../node/)
* class [NodeList](../)
* مساحة الاسم [Aspose.Words](../../nodelist/)
* المجسم [Aspose.Words](../../../)


