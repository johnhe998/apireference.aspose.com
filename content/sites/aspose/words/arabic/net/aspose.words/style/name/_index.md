---
title: Style.Name
second_title: Aspose.Words لمراجع .NET API
description: Style ملكية. الحصول على اسم النمط أو تحديده.
type: docs
weight: 110
url: /ar/net/aspose.words/style/name/
---
## Style.Name property

الحصول على اسم النمط أو تحديده.

```csharp
public string Name { get; set; }
```

### ملاحظات

لا يمكن أن تكون سلسلة فارغة.

إذا كان هناك بالفعل نمط بهذا الاسم في المجموعة ، فإن هذا النمط سيتجاوزه. ستشير جميع العقد المتأثرة إلى نمط جديد.

### أمثلة

يوضح كيفية الوصول إلى مجموعة أنماط المستند.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// تعداد وإدراج جميع الأنماط التي تم إنشاؤها باستخدام Aspose.Words تحتوي على كل الأنماط التي تم إنشاؤها باستخدام Aspose.Words بشكل افتراضي.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

يوضح كيفية استنساخ نمط المستند.

```csharp
Document doc = new Document();

// تقوم طريقة AddCopy بإنشاء نسخة من النمط المحدد و
// ينشئ تلقائيًا اسمًا جديدًا للنمط ، مثل "العنوان 1_0".
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// استخدم خاصية "الاسم" الخاصة بالنمط لتغيير اسم تعريف النمط.
newStyle.Name = "My Heading 1";

// يحتوي المستند الآن على نمطين متطابقين المظهر بأسماء مختلفة.
// تغيير إعدادات أحد الأنماط لا يؤثر على الآخر.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### أنظر أيضا

* class [Style](../)
* مساحة الاسم [Aspose.Words](../../style/)
* المجسم [Aspose.Words](../../../)


