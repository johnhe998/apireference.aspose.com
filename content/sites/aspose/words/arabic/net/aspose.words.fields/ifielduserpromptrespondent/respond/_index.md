---
title: IFieldUserPromptRespondent.Respond
second_title: Aspose.Words لمراجع .NET API
description: IFieldUserPromptRespondent طريقة. عند التنفيذ  يتم إرجاع استجابة من المستخدم عند المطالبة. يجب أن يعود التنفيذ لا شيء للإشارة إلى أن المستخدم لم يستجب إلى المطالبة أي أن المستخدم قد ضغط على زر إلغاء في نافذة المطالبة .
type: docs
weight: 10
url: /ar/net/aspose.words.fields/ifielduserpromptrespondent/respond/
---
## IFieldUserPromptRespondent.Respond method

عند التنفيذ ، يتم إرجاع استجابة من المستخدم عند المطالبة. يجب أن يعود التنفيذ **لا شيء** للإشارة إلى أن المستخدم لم يستجب إلى المطالبة (أي أن المستخدم قد ضغط على زر "إلغاء" في نافذة المطالبة) .

```csharp
public string Respond(string promptText, string defaultResponse)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| promptText | String | نص موجه (أي عنوان نافذة المطالبة). |
| defaultResponse | String | استجابة المستخدم الافتراضية (أي القيمة الأولية الواردة في نافذة المطالبة). |

### قيمة الإرجاع

استجابة المستخدم (أي القيمة المؤكدة الواردة في نافذة المطالبة).

### أمثلة

يوضح كيفية إنشاء حقل ASK وتعيين خصائصه.

```csharp
[Test]
public void FieldAsk()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // ضع حقلاً حيث سيتم وضع الرد على حقل ASK الخاص بنا.
    FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    fieldRef.BookmarkName = "MyAskField";
    builder.Writeln();

    Assert.AreEqual(" REF  MyAskField", fieldRef.GetFieldCode());

    // أدخل حقل ASK وقم بتحرير خصائصه للإشارة إلى حقل REF الخاص بنا عن طريق اسم الإشارة المرجعية.
    FieldAsk fieldAsk = (FieldAsk)builder.InsertField(FieldType.FieldAsk, true);
    fieldAsk.BookmarkName = "MyAskField";
    fieldAsk.PromptText = "Please provide a response for this ASK field";
    fieldAsk.DefaultResponse = "Response from within the field.";
    fieldAsk.PromptOnceOnMailMerge = true;
    builder.Writeln();

    Assert.AreEqual(
        " ASK  MyAskField \"Please provide a response for this ASK field\" \\d \"Response from within the field.\" \\o",
        fieldAsk.GetFieldCode());

    // تطبق حقول ASK الاستجابة الافتراضية لحقول REF الخاصة بها أثناء دمج المراسلات.
    DataTable table = new DataTable("My Table");
    table.Columns.Add("Column 1");
    table.Rows.Add("Row 1");
    table.Rows.Add("Row 2");

    FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    fieldMergeField.FieldName = "Column 1";

    // يمكننا تعديل الاستجابة الافتراضية أو تجاوزها في حقول ASK باستخدام مستجيب موجه مخصص ،
    // الذي سيحدث أثناء دمج البريد.
    doc.FieldOptions.UserPromptRespondent = new MyPromptRespondent();
    doc.MailMerge.Execute(table);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.ASK.docx");

/// <summary>
/// يسبق النص للاستجابة الافتراضية لحقل ASK أثناء دمج البريد.
/// </summary>
private class MyPromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response from MyPromptRespondent. " + defaultResponse;
    }
}
```

### أنظر أيضا

* interface [IFieldUserPromptRespondent](../)
* مساحة الاسم [Aspose.Words.Fields](../../ifielduserpromptrespondent/)
* المجسم [Aspose.Words](../../../)


