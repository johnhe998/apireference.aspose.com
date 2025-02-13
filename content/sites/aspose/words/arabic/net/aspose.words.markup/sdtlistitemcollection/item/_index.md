---
title: SdtListItemCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: SdtListItemCollection ملكية. إرجاع أSdtListItem كائن نظرًا لمؤشره الصفري في المجموعة.
type: docs
weight: 20
url: /ar/net/aspose.words.markup/sdtlistitemcollection/item/
---
## SdtListItemCollection indexer

إرجاع أ[`SdtListItem`](../../sdtlistitem/) كائن نظرًا لمؤشره الصفري في المجموعة.

```csharp
public SdtListItem this[int index] { get; }
```

### أمثلة

يوضح كيفية العمل مع علامات المستندات المهيكلة للقائمة المنسدلة.

```csharp
Document doc = new Document();
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.DropDownList, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// علامة المستند المهيكلة القائمة المنسدلة هي نموذج يسمح للمستخدم
// حدد خيارًا من قائمة بالنقر بزر الماوس الأيسر وفتح النموذج في Microsoft Word.
// تحتوي الخاصية "ListItems" على كافة عناصر القائمة ، ويكون كل عنصر قائمة "SdtListItem".
SdtListItemCollection listItems = tag.ListItems;
listItems.Add(new SdtListItem("Value 1"));

Assert.AreEqual(listItems[0].DisplayText, listItems[0].Value);

// أضف 3 عناصر قائمة أخرى. قم بتهيئة هذه العناصر باستخدام مُنشئ مختلف للعنصر الأول
// لعرض سلاسل مختلفة عن قيمها.
listItems.Add(new SdtListItem("Item 2", "Value 2"));
listItems.Add(new SdtListItem("Item 3", "Value 3"));
listItems.Add(new SdtListItem("Item 4", "Value 4"));

Assert.AreEqual(4, listItems.Count);

// تعرض القائمة المنسدلة العنصر الأول. قم بتعيين عنصر قائمة مختلف إلى "SelectedValue" لعرضه.
listItems.SelectedValue = listItems[3];

Assert.AreEqual("Value 4", listItems.SelectedValue.Value);

// تعداد المجموعة وطباعة كل عنصر.
using (IEnumerator<SdtListItem> enumerator = listItems.GetEnumerator())
{
    while (enumerator.MoveNext())
        if (enumerator.Current != null)
            Console.WriteLine($"List item: {enumerator.Current.DisplayText}, value: {enumerator.Current.Value}");
}

 // إزالة عنصر القائمة الأخير.
listItems.RemoveAt(3);

Assert.AreEqual(3, listItems.Count);

// نظرًا لأن عنصر التحكم في القائمة المنسدلة مضبوط على عرض العنصر الذي تمت إزالته افتراضيًا ، فامنحه عنصرًا للعرض موجودًا.
listItems.SelectedValue = listItems[1];

doc.Save(ArtifactsDir + "StructuredDocumentTag.ListItemCollection.docx");

// استخدم طريقة "المسح" لتفريغ مجموعة العناصر المنسدلة بالكامل مرة واحدة.
listItems.Clear();

Assert.AreEqual(0, listItems.Count);
```

### أنظر أيضا

* class [SdtListItem](../../sdtlistitem/)
* class [SdtListItemCollection](../)
* مساحة الاسم [Aspose.Words.Markup](../../sdtlistitemcollection/)
* المجسم [Aspose.Words](../../../)


