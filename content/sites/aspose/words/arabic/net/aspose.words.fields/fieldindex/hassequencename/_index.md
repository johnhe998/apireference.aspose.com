---
title: FieldIndex.HasSequenceName
second_title: Aspose.Words لمراجع .NET API
description: FieldIndex ملكية. يحصل على قيمة تشير إلى ما إذا كان يجب استخدام تسلسل أثناء بناء نتيجة الحقل.
type: docs
weight: 60
url: /ar/net/aspose.words.fields/fieldindex/hassequencename/
---
## FieldIndex.HasSequenceName property

يحصل على قيمة تشير إلى ما إذا كان يجب استخدام تسلسل أثناء بناء نتيجة الحقل.

```csharp
public bool HasSequenceName { get; }
```

### أمثلة

يوضح كيفية تقسيم مستند إلى أجزاء من خلال الجمع بين حقلي INDEX و SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// إذا كانت حقول XE لها نفس القيمة في خاصية "النص" الخاصة بها ،
// سيجمعها الحقل INDEX في إدخال واحد.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// في خاصية SequenceName ، قم بتسمية تسلسل حقل SEQ. سيتم الآن عرض كل إدخال في هذا الحقل INDEX أيضًا
// الرقم الذي يوجد به حساب التسلسل في موقع حقل XE الذي أنشأ هذا الإدخال.
index.SequenceName = "MySequence";

// تعيين النص الذي يدور حول التسلسل وأرقام الصفحات لشرح معناها للمستخدم.
// سيعرض الإدخال الذي تم إنشاؤه باستخدام هذا التكوين شيئًا مثل "MySequence at 1 في الصفحة 1" في رقم صفحته.
لا يمكن أن يزيد طول // PageNumberSeparator و SequenceSeparator عن 15 حرفًا.
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// تعرض حقول SEQ عددًا يتزايد في كل حقل SEQ.
// تحتفظ هذه الحقول أيضًا بأعداد منفصلة لكل تسلسل مسمى فريد
// التي تم تحديدها بواسطة خاصية "SequenceIdentifier" لحقل SEQ.
// أدخل حقل SEQ الذي ينقل تسلسل "MySequence" إلى 1.
// لا يختلف هذا الحقل عن نص المستند العادي. لن يظهر في جدول محتويات حقل INDEX.
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// أدخل حقل XE الذي سينشئ إدخالًا في الحقل INDEX.
// نظرًا لأن "MySequence" في 1 وحقل XE هذا في الصفحة 2 ، جنبًا إلى جنب مع الفواصل المخصصة التي حددناها أعلاه ،
// سيعرض إدخال INDEX لهذا الحقل "Cat" على الجانب الأيسر ، و "MySequence at 1 في الصفحة 2" على اليمين.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// أدخل فاصل صفحة واستخدم حقول SEQ لتقدم "MySequence" إلى 3.
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// أدخل حقل XE بنفس خاصية النص كما هو مذكور أعلاه.
// سيقوم إدخال INDEX بتجميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
// نظرًا لأننا في الصفحة 2 مع "MySequence" في 3 ، "، 3 في الصفحة 3" سيتم إلحاقها بإدخال INDEX نفسه على النحو الوارد أعلاه.
// سيعرض جزء رقم الصفحة في إدخال INDEX الآن "MySequence at 1 في الصفحة 2 ، 3 في الصفحة 3".
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// أدخل حقل XE بقيمة خاصية نص جديدة وفريدة من نوعها.
// سيؤدي هذا إلى إضافة إدخال جديد ، مع MySequence في 3 في الصفحة 4.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### أنظر أيضا

* class [FieldIndex](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldindex/)
* المجسم [Aspose.Words](../../../)


