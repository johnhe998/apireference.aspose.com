---
title: DropDownItemCollection.GetEnumerator
second_title: Aspose.Words لمراجع .NET API
description: DropDownItemCollection طريقة. إرجاع كائن العداد الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة.
type: docs
weight: 60
url: /ar/net/aspose.words.fields/dropdownitemcollection/getenumerator/
---
## DropDownItemCollection.GetEnumerator method

إرجاع كائن العداد الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة.

```csharp
public IEnumerator<string> GetEnumerator()
```

### أمثلة

يوضح كيفية إدراج حقل مربع تحرير وسرد وتحرير العناصر في مجموعة العناصر الخاصة به.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل مربع تحرير وسرد ، ثم تحقق من مجموعة العناصر المنسدلة الخاصة به.
// في Microsoft Word ، سينقر المستخدم على مربع التحرير والسرد ،
// ثم اختر أحد عناصر النص في المجموعة لعرضها.
string[] items = { "One", "Two", "Three" };
FormField comboBoxField = builder.InsertComboBox("DropDown", items, 0);
DropDownItemCollection dropDownItems = comboBoxField.DropDownItems;

Assert.AreEqual(3, dropDownItems.Count);
Assert.AreEqual("One", dropDownItems[0]);
Assert.AreEqual(1, dropDownItems.IndexOf("Two"));
Assert.IsTrue(dropDownItems.Contains("Three"));

// هناك طريقتان لإضافة عنصر جديد إلى مجموعة موجودة من عناصر المربع المنسدل.
// 1 - إلحاق عنصر بنهاية المجموعة:
dropDownItems.Add("Four");

// 2 - أدخل عنصرًا قبل عنصر آخر في فهرس محدد:
dropDownItems.Insert(3, "Three and a half");

Assert.AreEqual(5, dropDownItems.Count);

// تكرار على المجموعة وطباعة كل عنصر.
using (IEnumerator<string> dropDownCollectionEnumerator = dropDownItems.GetEnumerator())
    while (dropDownCollectionEnumerator.MoveNext())
        Console.WriteLine(dropDownCollectionEnumerator.Current);

// توجد طريقتان لإزالة العناصر من مجموعة عناصر قائمة منسدلة.
// 1 - إزالة عنصر بمحتويات مساوية للسلسلة التي تم تمريرها:
dropDownItems.Remove("Four");

// 2 - إزالة عنصر في فهرس:
dropDownItems.RemoveAt(3);

Assert.AreEqual(3, dropDownItems.Count);
Assert.IsFalse(dropDownItems.Contains("Three and a half"));
Assert.IsFalse(dropDownItems.Contains("Four"));

doc.Save(ArtifactsDir + "FormFields.DropDownItemCollection.html");

// إفراغ المجموعة الكاملة للعناصر المنسدلة.
dropDownItems.Clear();
```

### أنظر أيضا

* class [DropDownItemCollection](../)
* مساحة الاسم [Aspose.Words.Fields](../../dropdownitemcollection/)
* المجسم [Aspose.Words](../../../)


