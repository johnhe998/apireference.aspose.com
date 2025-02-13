---
title: Class VariableCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.VariableCollection فصل. مجموعة من متغيرات المستند.
type: docs
weight: 6230
url: /ar/net/aspose.words/variablecollection/
---
## VariableCollection class

مجموعة من متغيرات المستند.

```csharp
public class VariableCollection : IEnumerable<KeyValuePair<string, string>>
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/variablecollection/count/) { get; } | الحصول على عدد العناصر الموجودة في المجموعة. |
| [Item](../../aspose.words/variablecollection/item/) { get; set; } | الحصول على متغير مستند أو تعيينه حسب الاسم غير الحساس لحالة الأحرف. _ القيم الفارغة غير مسموح بها كجانب يمين من المهمة وسيتم استبدالها بسلسلة فارغة. (2 indexers) |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words/variablecollection/add/)(string, string) | يضيف متغير مستند إلى المجموعة. |
| [Clear](../../aspose.words/variablecollection/clear/)() | يزيل كل العناصر من المجموعة. |
| [Contains](../../aspose.words/variablecollection/contains/)(string) | لتحديد ما إذا كانت المجموعة تحتوي على متغير مستند بالاسم المحدد. |
| [GetEnumerator](../../aspose.words/variablecollection/getenumerator/)() | إرجاع كائن العداد الذي يمكن استخدامه للتكرار على جميع المتغيرات في المجموعة. |
| [IndexOfKey](../../aspose.words/variablecollection/indexofkey/)(string) | إرجاع الفهرس الصفري لمتغير المستند المحدد في المجموعة. |
| [Remove](../../aspose.words/variablecollection/remove/)(string) | يزيل متغير مستند بالاسم المحدد من المجموعة. |
| [RemoveAt](../../aspose.words/variablecollection/removeat/)(int) | يزيل متغير مستند في الفهرس المحدد. |

### ملاحظات

أسماء المتغيرات والقيم هي سلاسل.

أسماء المتغيرات غير حساسة لحالة الأحرف.

### أمثلة

يوضح كيفية العمل مع مجموعة متغيرات المستند.

```csharp
Document doc = new Document();
VariableCollection variables = doc.Variables;

// يحتوي كل مستند على مجموعة من متغيرات زوج المفتاح / القيمة ، والتي يمكننا إضافة عناصر إليها.
variables.Add("Home address", "123 Main St.");
variables.Add("City", "London");
variables.Add("Bedrooms", "3");

Assert.AreEqual(3, variables.Count);

// يمكننا عرض قيم المتغيرات في نص المستند باستخدام حقول DOCVARIABLE.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocVariable field = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
field.VariableName = "Home address";
field.Update();

Assert.AreEqual("123 Main St.", field.Result);

// سيؤدي تعيين قيم للمفاتيح الموجودة إلى تحديثها.
variables.Add("Home address", "456 Queen St.");

// سيتعين علينا بعد ذلك تحديث حقول DOCVARIABLE للتأكد من أنها تعرض قيمة محدثة.
Assert.AreEqual("123 Main St.", field.Result);

field.Update();

Assert.AreEqual("456 Queen St.", field.Result);

// تحقق من وجود متغيرات المستند باسم أو قيمة معينة.
Assert.True(variables.Contains("City"));
Assert.True(variables.Any(v => v.Value == "London"));

// تقوم مجموعة المتغيرات تلقائيًا بفرز المتغيرات أبجديًا بالاسم.
Assert.AreEqual(0, variables.IndexOfKey("Bedrooms"));
Assert.AreEqual(1, variables.IndexOfKey("City"));
Assert.AreEqual(2, variables.IndexOfKey("Home address"));

// عد على مجموعة المتغيرات.
using (IEnumerator<KeyValuePair<string, string>> enumerator = doc.Variables.GetEnumerator())
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: {enumerator.Current.Key}, Value: {enumerator.Current.Value}");

// فيما يلي ثلاث طرق لإزالة متغيرات المستند من مجموعة.
// 1 - بالاسم:
variables.Remove("City");

Assert.False(variables.Contains("City"));

// 2 - حسب الفهرس:
variables.RemoveAt(1);

Assert.False(variables.Contains("Home address"));

// 3 - امسح المجموعة بأكملها مرة واحدة:
variables.Clear();

Assert.That(variables, Is.Empty);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


