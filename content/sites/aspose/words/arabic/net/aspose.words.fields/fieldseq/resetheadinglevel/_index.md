---
title: FieldSeq.ResetHeadingLevel
second_title: Aspose.Words لمراجع .NET API
description: FieldSeq ملكية. الحصول على أو تعيين رقم صحيح يمثل مستوى العنوان لإعادة تعيين رقم التسلسل إلى . إرجاع 1 إذا كان الرقم غائبًا .
type: docs
weight: 40
url: /ar/net/aspose.words.fields/fieldseq/resetheadinglevel/
---
## FieldSeq.ResetHeadingLevel property

الحصول على أو تعيين رقم صحيح يمثل مستوى العنوان لإعادة تعيين رقم التسلسل إلى . إرجاع -1 إذا كان الرقم غائبًا .

```csharp
public string ResetHeadingLevel { get; set; }
```

### أمثلة

يظهر إنشاء الترقيم باستخدام حقول SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تعرض حقول SEQ عددًا يتزايد في كل حقل SEQ.
// تحتفظ هذه الحقول أيضًا بأعداد منفصلة لكل تسلسل مسمى فريد
// التي تم تحديدها بواسطة خاصية "SequenceIdentifier" لحقل SEQ.
// أدخل حقل SEQ يعرض قيمة العدد الحالية لـ "MySequence" ،
// بعد استخدام خاصية "ResetNumber" لتعيينها على 100.
builder.Write("#");
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetNumber = "100";
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\r 100", fieldSeq.GetFieldCode());
Assert.AreEqual("100", fieldSeq.Result);

// اعرض الرقم التالي في هذا التسلسل مع حقل SEQ آخر.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.Update();

Assert.AreEqual("101", fieldSeq.Result);

// أدخل عنوان المستوى 1.
builder.InsertBreak(BreakType.ParagraphBreak);
builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("This level 1 heading will reset MySequence to 1");
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// أدخل حقل SEQ آخر من نفس التسلسل وقم بتكوينه لإعادة تعيين العد في كل عنوان بـ 1.
builder.Write("\n#");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetHeadingLevel = "1";
fieldSeq.Update();

// العنوان أعلاه هو عنوان من المستوى 1 ، لذلك يتم إعادة تعيين عدد هذا التسلسل إلى 1.
Assert.AreEqual(" SEQ  MySequence \\s 1", fieldSeq.GetFieldCode());
Assert.AreEqual("1", fieldSeq.Result);

// الانتقال إلى الرقم التالي من هذا التسلسل.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.InsertNextNumber = true;
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\n", fieldSeq.GetFieldCode());
Assert.AreEqual("2", fieldSeq.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SEQ.ResetNumbering.docx");
```

### أنظر أيضا

* class [FieldSeq](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldseq/)
* المجسم [Aspose.Words](../../../)


