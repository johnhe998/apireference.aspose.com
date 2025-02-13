---
title: MailMerge.GetFieldNamesForRegion
second_title: Aspose.Words لمراجع .NET API
description: MailMerge طريقة. إرجاع مجموعة من أسماء حقول دمج المراسلات المتوفرة في المنطقة.
type: docs
weight: 230
url: /ar/net/aspose.words.mailmerging/mailmerge/getfieldnamesforregion/
---
## GetFieldNamesForRegion(string) {#getfieldnamesforregion}

إرجاع مجموعة من أسماء حقول دمج المراسلات المتوفرة في المنطقة.

```csharp
public string[] GetFieldNamesForRegion(string regionName)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| regionName | String | اسم المنطقة (غير حساس لحالة الأحرف). |

### ملاحظات

إرجاع أسماء حقول الدمج الكاملة بما في ذلك البادئة الاختيارية. لا يزيل أسماء الحقول المكررة.

إذا كان المستند يحتوي على مناطق متعددة بنفس الاسم ، فستتم معالجة المنطقة الأولى.

يتم إنشاء مجموعة سلسلة جديدة في كل مكالمة.

### أمثلة

يوضح كيفية إنشاء مناطق دمج المراسلات وسردها وقراءتها.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "TableStart" و "TableEnd" ، اللتان تدخلان داخل MERGEFIELDs ،
// تشير إلى السلاسل التي تشير إلى بدايات ونهايات مناطق دمج البريد.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// استخدم هذه العلامات لبدء وإنهاء منطقة دمج المراسلات المسماة "MailMergeRegion1" ،
// التي ستحتوي على MERGEFIELDs لعمودين.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// يمكننا تتبع مناطق الدمج وأعمدتها من خلال النظر إلى هذه المجموعات.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// أدخل منطقة بنفس الاسم داخل المنطقة الحالية ، مما سيجعلها أمة.
// الآن سيكون حقل "Column2" داخل منطقة جديدة.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// إذا بحثنا عن اسم المناطق المكررة باستخدام طريقة "GetRegionsByName" ،
// سيعيد كل هذه المناطق في مجموعة.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// تحقق من أن المنطقة الثانية بها الآن منطقة أصلية.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### أنظر أيضا

* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)

---

## GetFieldNamesForRegion(string, int) {#getfieldnamesforregion_1}

إرجاع مجموعة من أسماء حقول دمج المراسلات المتوفرة في المنطقة.

```csharp
public string[] GetFieldNamesForRegion(string regionName, int regionIndex)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| regionName | String | اسم المنطقة (غير حساس لحالة الأحرف). |
| regionIndex | Int32 | مؤشر المنطقة (على أساس الصفر). |

### ملاحظات

إرجاع أسماء حقول الدمج الكاملة بما في ذلك البادئة الاختيارية. لا يزيل أسماء الحقول المكررة.

إذا كان المستند يحتوي على مناطق متعددة بنفس الاسم ، فستتم معالجة المنطقة N (على أساس الصفر).

يتم إنشاء مجموعة سلسلة جديدة في كل مكالمة.

### أمثلة

يوضح كيفية إنشاء مناطق دمج المراسلات وسردها وقراءتها.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "TableStart" و "TableEnd" ، اللتان تدخلان داخل MERGEFIELDs ،
// تشير إلى السلاسل التي تشير إلى بدايات ونهايات مناطق دمج البريد.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// استخدم هذه العلامات لبدء وإنهاء منطقة دمج المراسلات المسماة "MailMergeRegion1" ،
// التي ستحتوي على MERGEFIELDs لعمودين.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// يمكننا تتبع مناطق الدمج وأعمدتها من خلال النظر إلى هذه المجموعات.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// أدخل منطقة بنفس الاسم داخل المنطقة الحالية ، مما سيجعلها أمة.
// الآن سيكون حقل "Column2" داخل منطقة جديدة.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// إذا بحثنا عن اسم المناطق المكررة باستخدام طريقة "GetRegionsByName" ،
// سيعيد كل هذه المناطق في مجموعة.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// تحقق من أن المنطقة الثانية بها الآن منطقة أصلية.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### أنظر أيضا

* class [MailMerge](../)
* مساحة الاسم [Aspose.Words.MailMerging](../../mailmerge/)
* المجسم [Aspose.Words](../../../)


