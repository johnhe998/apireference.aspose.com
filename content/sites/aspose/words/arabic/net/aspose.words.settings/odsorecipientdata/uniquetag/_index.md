---
title: OdsoRecipientData.UniqueTag
second_title: Aspose.Words لمراجع .NET API
description: OdsoRecipientData ملكية. يحدد محتويات سجل معين في العمود الذي يحتوي على بيانات فريدة. القيمة الافتراضية هيلا شيء .
type: docs
weight: 50
url: /ar/net/aspose.words.settings/odsorecipientdata/uniquetag/
---
## OdsoRecipientData.UniqueTag property

يحدد محتويات سجل معين في العمود الذي يحتوي على بيانات فريدة. القيمة الافتراضية هي`لا شيء` .

```csharp
public byte[] UniqueTag { get; set; }
```

### أمثلة

يوضح كيفية الوصول إلى مجموعة البيانات التي تحدد سجلات مصدر بيانات الدمج التي سيستبعدها دمج المراسلات.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

OdsoRecipientDataCollection dataCollection = doc.MailMergeSettings.Odso.RecipientDatas;

Assert.AreEqual(70, dataCollection.Count);

using (IEnumerator<OdsoRecipientData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine(
            $"Odso recipient data index {index++} will {(enumerator.Current.Active ? "" : "not ")}be imported upon mail merge.");
        Console.WriteLine($"\tColumn #{enumerator.Current.Column}");
        Console.WriteLine($"\tHash code: {enumerator.Current.Hash}");
        Console.WriteLine($"\tContents array length: {enumerator.Current.UniqueTag.Length}");
    }
}

// يمكننا استنساخ العناصر في هذه المجموعة.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// يمكننا أيضًا إزالة العناصر بشكل فردي ، أو مسح المجموعة بأكملها مرة واحدة.
dataCollection.RemoveAt(0);

Assert.AreEqual(69, dataCollection.Count);

dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### أنظر أيضا

* class [OdsoRecipientData](../)
* مساحة الاسم [Aspose.Words.Settings](../../odsorecipientdata/)
* المجسم [Aspose.Words](../../../)


