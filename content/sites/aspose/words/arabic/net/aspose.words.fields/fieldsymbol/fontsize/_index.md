---
title: FieldSymbol.FontSize
second_title: Aspose.Words لمراجع .NET API
description: FieldSymbol ملكية. الحصول على أو تحديد الحجم بالنقاط الخاصة بخط الحرف الذي تم استرجاعه بواسطة الحقل.
type: docs
weight: 50
url: /ar/net/aspose.words.fields/fieldsymbol/fontsize/
---
## FieldSymbol.FontSize property

الحصول على أو تحديد الحجم بالنقاط الخاصة بخط الحرف الذي تم استرجاعه بواسطة الحقل.

```csharp
public string FontSize { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقل SYMBOL.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي ثلاث طرق لاستخدام حقل SYMBOL لعرض حرف واحد.
// 1 - أضف حقل SYMBOL الذي يعرض رمز © (حقوق النشر) المحدد بواسطة رمز حرف ANSI:
FieldSymbol field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// رمز حرف ANSI "U + 00A9" أو "169" في شكل عدد صحيح محجوز لرمز حقوق النشر.
field.CharacterCode = 0x00a9.ToString();
field.IsAnsi = true;

Assert.AreEqual(" SYMBOL  169 \\a", field.GetFieldCode());

builder.Writeln(" Line 1");

// 2 - أضف حقل SYMBOL الذي يعرض الرمز ∞ (اللانهاية) ، وقم بتعديل مظهره:
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);

// في Unicode ، يحتل رمز اللانهاية الكود "221E".
field.CharacterCode = 0x221E.ToString();
field.IsUnicode = true;

// تغيير خط رمزنا بعد استخدام مخطط توزيع الأحرف في Windows
// للتأكد من أن الخط يمكن أن يمثل هذا الرمز.
field.FontName = "Calibri";
field.FontSize = "24";

// يمكننا تعيين هذا العلم للرموز الطويلة حتى لا يدفعوا بقية النص لأسفل على السطر.
field.DontAffectsLineSpacing = true;

Assert.AreEqual(" SYMBOL  8734 \\u \\f Calibri \\s 24 \\h", field.GetFieldCode());

builder.Writeln("Line 2");

// 3 - أضف حقل SYMBOL الذي يعرض الحرف ،
// بخط يدعم صفحة الترميز اللغوي Shift-JIS (Windows-932):
field = (FieldSymbol)builder.InsertField(FieldType.FieldSymbol, true);
field.FontName = "MS Gothic";
field.CharacterCode = 0x82A0.ToString();
field.IsShiftJis = true;

Assert.AreEqual(" SYMBOL  33440 \\f \"MS Gothic\" \\j", field.GetFieldCode());

builder.Write("Line 3");

doc.Save(ArtifactsDir + "Field.SYMBOL.docx");
```

### أنظر أيضا

* class [FieldSymbol](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldsymbol/)
* المجسم [Aspose.Words](../../../)


