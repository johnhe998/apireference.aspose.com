---
title: FieldNextIf.ComparisonOperator
second_title: Aspose.Words لمراجع .NET API
description: FieldNextIf ملكية. الحصول على عامل المقارنة أو تعيينه.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldnextif/comparisonoperator/
---
## FieldNextIf.ComparisonOperator property

الحصول على عامل المقارنة أو تعيينه.

```csharp
public string ComparisonOperator { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقول NEXT / NEXTIF لدمج عدة صفوف في صفحة واحدة أثناء دمج المراسلات.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // إنشاء مصدر بيانات لدمج البريد الخاص بنا بثلاثة صفوف.
    // عادةً ما يؤدي دمج المراسلات الذي يستخدم هذا الجدول إلى إنشاء مستند من 3 صفحات.
    DataTable table = new DataTable("Employees");
    table.Columns.Add("Courtesy Title");
    table.Columns.Add("First Name");
    table.Columns.Add("Last Name");
    table.Rows.Add("Mr.", "John", "Doe");
    table.Rows.Add("Mrs.", "Jane", "Cardholder");
    table.Rows.Add("Mr.", "Joe", "Bloggs");

    InsertMergeFields(builder, "First row: ");

    // إذا كان لدينا عدة حقول دمج بنفس اسم الحقل ،
    // سيستقبلون البيانات من نفس الصف لمصدر البيانات ويعرضون نفس القيمة بعد الدمج.
    // يخبر الحقل التالي عملية دمج البريد على الفور بالتحرك لأسفل بمقدار صف واحد ،
    // مما يعني أن أي MERGEFIELDs التي تتبع الحقل التالي ستتلقى بيانات من الصف التالي.
    // تأكد من عدم محاولة التخطي إلى الصف التالي أثناء التواجد بالفعل في الصف الأخير.
    FieldNext fieldNext = (FieldNext)builder.InsertField(FieldType.FieldNext, true);

    Assert.AreEqual(" NEXT ", fieldNext.GetFieldCode());

    // بعد الدمج ، قيم مصدر البيانات التي تقبلها MERGEFIELDs
     // ستنتهي في نفس الصفحة مثل MERGEFIELDs أعلاه.
    InsertMergeFields(builder, "Second row: ");

    // يحتوي حقل NEXTIF على نفس وظيفة الحقل التالي ،
    // لكنه ينتقل إلى الصف التالي فقط إذا كانت العبارة التي تم إنشاؤها بواسطة الخصائص الثلاثة التالية صحيحة.
    FieldNextIf fieldNextIf = (FieldNextIf)builder.InsertField(FieldType.FieldNextIf, true);
    fieldNextIf.LeftExpression = "5";
    fieldNextIf.RightExpression = "2 + 3";
    fieldNextIf.ComparisonOperator = "=";

    Assert.AreEqual(" NEXTIF  5 = \"2 + 3\"", fieldNextIf.GetFieldCode());

    // إذا كانت المقارنة التي أكدها الحقل أعلاه صحيحة ،
    // ستأخذ حقول الدمج الثلاثة التالية البيانات من الصف الثالث.
    // خلاف ذلك ، ستأخذ هذه الحقول البيانات من الصف 2 مرة أخرى.
    InsertMergeFields(builder, "Third row: ");

    doc.MailMerge.Execute(table);

     // يحتوي مصدر البيانات لدينا على 3 صفوف ، وقد تخطينا الصفوف مرتين.
    // سيتضمن مستند الإخراج لدينا صفحة واحدة تحتوي على بيانات من جميع الصفوف الثلاثة.
    doc.Save(ArtifactsDir + "Field.NEXT.NEXTIF.docx");

/// <summary>
/// يستخدم منشئ المستندات لإدراج MERGEFIELDs لمصدر بيانات يحتوي على أعمدة باسم "Courtesy Title" و "First Name" و "Last Name".
/// </summary>
public void InsertMergeFields(DocumentBuilder builder, string firstFieldTextBefore)
{
    InsertMergeField(builder, "Courtesy Title", firstFieldTextBefore, " ");
    InsertMergeField(builder, "First Name", null, " ");
    InsertMergeField(builder, "Last Name", null, null);
    builder.InsertParagraph();
}

/// <summary>
/// يستخدم أداة إنشاء المستندات لإدراج MERRGEFIELD بخصائص محددة.
/// </summary>
public void InsertMergeField(DocumentBuilder builder, string fieldName, string textBefore, string textAfter)
{
    FieldMergeField field = (FieldMergeField) builder.InsertField(FieldType.FieldMergeField, true);
    field.FieldName = fieldName;
    field.TextBefore = textBefore;
    field.TextAfter = textAfter;
}
```

### أنظر أيضا

* class [FieldNextIf](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldnextif/)
* المجسم [Aspose.Words](../../../)


