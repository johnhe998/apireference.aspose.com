---
title: FieldPrint.PrinterInstructions
second_title: Aspose.Words لمراجع .NET API
description: FieldPrint ملكية. الحصول على أو تعيين أحرف رمز التحكم الخاصة بالطابعة أو إرشادات PostScript.
type: docs
weight: 30
url: /ar/net/aspose.words.fields/fieldprint/printerinstructions/
---
## FieldPrint.PrinterInstructions property

الحصول على أو تعيين أحرف رمز التحكم الخاصة بالطابعة أو إرشادات PostScript.

```csharp
public string PrinterInstructions { get; set; }
```

### أمثلة

يظهر لإدراج حقل PRINT.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// يمكن أن يرسل حقل PRINT إرشادات إلى الطابعة.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// قم بتعيين المنطقة الخاصة بالطابعة لتنفيذ التعليمات عليها.
// في هذه الحالة ، ستكون الفقرة التي تحتوي على حقل الطباعة الخاص بنا.
field.PostScriptGroup = "para";

// عندما نستخدم طابعة تدعم PostScript لطباعة وثيقتنا ،
// هذا الأمر سيحول المنطقة بأكملها التي حددناها في "field.PostScriptGroup" إلى اللون الأبيض.
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### أنظر أيضا

* class [FieldPrint](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldprint/)
* المجسم [Aspose.Words](../../../)


