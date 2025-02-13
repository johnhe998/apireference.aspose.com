---
title: FieldBarcode.PostalAddress
second_title: Aspose.Words لمراجع .NET API
description: FieldBarcode ملكية. الحصول على أو تعيين العنوان البريدي المستخدم لإنشاء رمز شريطي أو اسم الإشارة المرجعية التي تشير إليه.
type: docs
weight: 50
url: /ar/net/aspose.words.fields/fieldbarcode/postaladdress/
---
## FieldBarcode.PostalAddress property

الحصول على أو تعيين العنوان البريدي المستخدم لإنشاء رمز شريطي أو اسم الإشارة المرجعية التي تشير إليه.

```csharp
public string PostalAddress { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقل BARCODE لعرض الرموز البريدية الأمريكية في شكل رمز شريطي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// فيما يلي طريقتان لاستخدام حقول BARCODE لعرض القيم المخصصة كرموز شريطية.
// 1 - قم بتخزين القيمة التي سيعرضها الرمز الشريطي في خاصية PostalAddress:
FieldBarcode field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);

// يجب أن تكون هذه القيمة رمزًا بريديًا صالحًا.
field.PostalAddress = "96801";
field.IsUSPostalAddress = true;
field.FacingIdentificationMark = "C";

Assert.AreEqual(" BARCODE  96801 \\u \\f C", field.GetFieldCode());

builder.InsertBreak(BreakType.LineBreak);

// 2 - الإشارة إلى إشارة مرجعية تخزن القيمة التي سيعرضها هذا الرمز الشريطي:
field = (FieldBarcode)builder.InsertField(FieldType.FieldBarcode, true);
field.PostalAddress = "BarcodeBookmark";
field.IsBookmark = true;

Assert.AreEqual(" BARCODE  BarcodeBookmark \\b", field.GetFieldCode());

// الإشارة المرجعية التي يشير إليها الحقل BARCODE في خاصية PostalAddress الخاصة به
// يجب ألا يحتوي على أي شيء بخلاف الرمز البريدي الصالح.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("BarcodeBookmark");
builder.Writeln("968877");
builder.EndBookmark("BarcodeBookmark");

doc.Save(ArtifactsDir + "Field.BARCODE.docx");
```

### أنظر أيضا

* class [FieldBarcode](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldbarcode/)
* المجسم [Aspose.Words](../../../)


