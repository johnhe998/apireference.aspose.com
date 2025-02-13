---
title: FieldAutoNumLgl.RemoveTrailingPeriod
second_title: Aspose.Words لمراجع .NET API
description: FieldAutoNumLgl ملكية. الحصول على أو تحديد ما إذا كان سيتم عرض الرقم بدون نقطة لاحقة.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldautonumlgl/removetrailingperiod/
---
## FieldAutoNumLgl.RemoveTrailingPeriod property

الحصول على أو تحديد ما إذا كان سيتم عرض الرقم بدون نقطة لاحقة.

```csharp
public bool RemoveTrailingPeriod { get; set; }
```

### أمثلة

يوضح كيفية تنظيم مستند باستخدام حقول AUTONUMLGL.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    const string fillerText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
                              "\nUt enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ";

    // تعرض حقول AUTONUMLGL رقمًا يتزايد في كل حقل AUTONUMLGL ضمن مستوى العنوان الحالي.
    // تحتفظ هذه الحقول بعدد منفصل لكل مستوى عنوان ،
     // ويعرض كل حقل أيضًا عدد حقول AUTONUMLGL لجميع مستويات العناوين الموجودة أسفل مستوى الحقل الخاص به.
    // يؤدي تغيير العد لأي مستوى عنوان إلى إعادة تعيين التهم لجميع المستويات فوق هذا المستوى إلى 1.
    // هذا يسمح لنا بتنظيم وثيقتنا في شكل قائمة مخطط تفصيلي.
    // هذا هو أول حقل AUTONUMLGL بمستوى عنوان 1 ، ويعرض "1." في المستند.
    InsertNumberedClause(builder, "\tHeading 1", fillerText, StyleIdentifier.Heading1);

    // هذا هو حقل AUTONUMLGL الثاني عند مستوى عنوان 1 ، لذلك سيعرض "2.".
    InsertNumberedClause(builder, "\tHeading 2", fillerText, StyleIdentifier.Heading1);

    // هذا هو أول حقل AUTONUMLGL بمستوى عنوان 2 ،
    // وعدد AUTONUMLGL لمستوى العنوان أدناه هو "2" ، لذلك سيعرض "2.1.".
    InsertNumberedClause(builder, "\tHeading 3", fillerText, StyleIdentifier.Heading2);

     // هذا هو أول حقل AUTONUMLGL بمستوى عنوان 3.
    // يعمل بنفس طريقة الحقل أعلاه ، سيعرض "2.1.1.".
    InsertNumberedClause(builder, "\tHeading 4", fillerText, StyleIdentifier.Heading3);

    // هذا الحقل في مستوى عنوان 2 ، وعدد AUTONUMLGL الخاص به هو 2 ، لذلك سيعرض الحقل "2.2.".
    InsertNumberedClause(builder, "\tHeading 5", fillerText, StyleIdentifier.Heading2);

    // زيادة عدد AUTONUMLGL لمستوى عنوان أقل من هذا المستوى
    // أعاد تعيين العد لهذا المستوى بحيث يعرض هذا الحقل "2.2.1.".
    InsertNumberedClause(builder, "\tHeading 6", fillerText, StyleIdentifier.Heading3);

    foreach (FieldAutoNumLgl field in doc.Range.Fields.Where(f => f.Type == FieldType.FieldAutoNumLegal))
    {
        // الحرف الفاصل الذي يظهر في نتيجة الحقل مباشرة بعد الرقم ،
        // هي نقطة توقف كاملة بشكل افتراضي. إذا تركنا هذه الخاصية فارغة ،
        // سيعرض حقل AUTONUMLGL الأخير "2.2.1." في المستند.
        Assert.IsNull(field.SeparatorCharacter);

        // تعيين حرف فاصل مخصص وإزالة الفترة اللاحقة
        // سيغير مظهر هذا الحقل من "2.2.1." إلى "2: 2: 1".
        // سنطبق هذا على جميع الحقول التي أنشأناها.
        field.SeparatorCharacter = ":";
        field.RemoveTrailingPeriod = true;
        Assert.AreEqual(" AUTONUMLGL  \\s : \\e", field.GetFieldCode());
    }

    doc.Save(ArtifactsDir + "Field.AUTONUMLGL.docx");

/// <summary>
/// يستخدم أداة إنشاء المستندات لإدراج بند مرقم بواسطة حقل AUTONUMLGL.
/// </summary>
private static void InsertNumberedClause(DocumentBuilder builder, string heading, string contents, StyleIdentifier headingStyle)
{
    builder.InsertField(FieldType.FieldAutoNumLegal, true);
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = headingStyle;
    builder.Writeln(heading);

    // سينتمي هذا النص إلى حقل العدد القانوني التلقائي فوقه.
    // سينهار عندما نضغط على السهم بجوار حقل AUTONUMLGL المقابل في Microsoft Word.
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = StyleIdentifier.BodyText;
    builder.Writeln(contents);
}
```

### أنظر أيضا

* class [FieldAutoNumLgl](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldautonumlgl/)
* المجسم [Aspose.Words](../../../)


