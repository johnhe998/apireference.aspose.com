---
title: StyleCollection.AddCopy
second_title: Aspose.Words لمراجع .NET API
description: StyleCollection طريقة. نسخ نمط في هذه المجموعة .
type: docs
weight: 70
url: /ar/net/aspose.words/stylecollection/addcopy/
---
## StyleCollection.AddCopy method

نسخ نمط في هذه المجموعة .

```csharp
public Style AddCopy(Style style)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| style | Style | النمط المراد نسخه. |

### قيمة الإرجاع

النمط المنسوخ جاهز للاستخدام.

### ملاحظات

يمكن أن ينتمي النمط المراد نسخه إلى نفس المستند بالإضافة إلى مستند مختلف.

تم نسخ النمط المرتبط.

هذه الطريقة لا تنسخ الأنماط الأساسية.

إذا كانت المجموعة تحتوي بالفعل على نمط بنفس الاسم ، فسيتم إنشاء الاسم الجديد تلقائيًا عن طريق إضافة لاحقة "_number" تبدأ من 0 ، مثل "Normal_0" و "Heading 1_1" وما إلى ذلك. Use[`Name`](../../style/name/) setter لتغيير اسم النمط المستورد.

### أمثلة

يوضح كيفية استيراد نمط من مستند إلى مستند مختلف.

```csharp
Document srcDoc = new Document();

// إنشاء نمط مخصص للمستند المصدر.
Style srcStyle = srcDoc.Styles.Add(StyleType.Paragraph, "MyStyle");
srcStyle.Font.Color = Color.Red;

// استيراد النمط المخصص للمستند المصدر إلى المستند الوجهة.
Document dstDoc = new Document();
Style newStyle = dstDoc.Styles.AddCopy(srcStyle);

// النمط المستورد له مظهر مطابق لنمط المصدر الخاص به.
Assert.AreEqual("MyStyle", newStyle.Name);
Assert.AreEqual(Color.Red.ToArgb(), newStyle.Font.Color.ToArgb());
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

* class [Style](../../style/)
* class [StyleCollection](../)
* مساحة الاسم [Aspose.Words](../../stylecollection/)
* المجسم [Aspose.Words](../../../)


