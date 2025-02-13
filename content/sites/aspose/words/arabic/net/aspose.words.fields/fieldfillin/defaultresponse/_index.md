---
title: FieldFillIn.DefaultResponse
second_title: Aspose.Words لمراجع .NET API
description: FieldFillIn ملكية. الحصول على أو تعيين استجابة المستخدم الافتراضية القيمة الأولية الواردة في نافذة المطالبة.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldfillin/defaultresponse/
---
## FieldFillIn.DefaultResponse property

الحصول على أو تعيين استجابة المستخدم الافتراضية (القيمة الأولية الواردة في نافذة المطالبة).

```csharp
public string DefaultResponse { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقل FILLIN لمطالبة المستخدم بالرد.

```csharp
public void FieldFillIn()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // أدخل حقل FILLIN. عندما نقوم بتحديث هذا الحقل يدويًا في Microsoft Word ،
    // سيطلب منا إدخال رد. سيعرض الحقل بعد ذلك الاستجابة كنص.
    FieldFillIn field = (FieldFillIn)builder.InsertField(FieldType.FieldFillIn, true);
    field.PromptText = "Please enter a response:";
    field.DefaultResponse = "A default response.";

    // يمكننا أيضًا استخدام هذه الحقول لمطالبة المستخدم بإجابة فريدة لكل صفحة
    // تم إنشاؤه أثناء دمج المراسلات باستخدام Microsoft Word.
    field.PromptOnceOnMailMerge = true;

    Assert.AreEqual(" FILLIN  \"Please enter a response:\" \\d \"A default response.\" \\o", field.GetFieldCode());

    FieldMergeField mergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    mergeField.FieldName = "MergeField";

    // إذا أجرينا عملية دمج بريد برمجيًا ، فيمكننا استخدام مستجيب موجه مخصص
    // لتحرير الاستجابات لحقول FILLIN التي يواجهها دمج المراسلات تلقائيًا.
    doc.FieldOptions.UserPromptRespondent = new PromptRespondent();
    doc.MailMerge.Execute(new [] { "MergeField" }, new object[] { "" });

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.FILLIN.docx");

/// <summary>
/// يسبق سطر للاستجابة الافتراضية لكل حقل FILLIN أثناء دمج المراسلات.
/// </summary>
private class PromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response modified by PromptRespondent. " + defaultResponse;
    }
}
```

### أنظر أيضا

* class [FieldFillIn](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldfillin/)
* المجسم [Aspose.Words](../../../)


