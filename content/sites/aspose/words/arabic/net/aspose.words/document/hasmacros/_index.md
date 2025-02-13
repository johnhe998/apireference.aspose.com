---
title: Document.HasMacros
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. عوائد حقيقي إذا كان المستند يحتوي على مشروع VBA وحدات ماكرو .
type: docs
weight: 190
url: /ar/net/aspose.words/document/hasmacros/
---
## Document.HasMacros property

عوائد **حقيقي** إذا كان المستند يحتوي على مشروع VBA (وحدات ماكرو) .

```csharp
public bool HasMacros { get; }
```

### أمثلة

يوضح كيفية استخدام حقول MACROBUTTON للسماح لنا بتشغيل وحدات ماكرو للمستند عن طريق النقر فوق.

```csharp
Document doc = new Document(MyDir + "Macro.docm");
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.IsTrue(doc.HasMacros);

// أدخل حقل MACROBUTTON ، وقم بالإشارة إلى أحد وحدات الماكرو الخاصة بالمستند بالاسم في خاصية MacroName.
FieldMacroButton field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "MyMacro";
field.DisplayText = "Double click to run macro: " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  MyMacro Double click to run macro: MyMacro", field.GetFieldCode());

// استخدم الخاصية للإشارة إلى "ViewZoom200" ، وهو ماكرو يأتي مع Microsoft Word.
// يمكننا العثور على كافة وحدات الماكرو الأخرى عبر View - >; وحدات الماكرو (القائمة المنسدلة) - >. عرض وحدات الماكرو.
// في تلك القائمة ، حدد "أوامر Word" من القائمة المنسدلة "وحدات الماكرو في:".
// إذا كان وثيقتنا تحتوي على ماكرو مخصص بنفس اسم ماكرو مخزون ،
// سيكون الماكرو الخاص بنا هو الذي يتم تشغيله في حقل MACROBUTTON.
builder.InsertParagraph();
field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "ViewZoom200";
field.DisplayText = "Run " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  ViewZoom200 Run ViewZoom200", field.GetFieldCode());

// احفظ المستند كنوع مستند ممكن بماكرو.
doc.Save(ArtifactsDir + "Field.MACROBUTTON.docm");
```

### أنظر أيضا

* method [RemoveMacros](../removemacros/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


