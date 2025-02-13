---
title: FieldSet.BookmarkName
second_title: Aspose.Words لمراجع .NET API
description: FieldSet ملكية. الحصول على اسم الإشارة المرجعية أو تعيينه.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldset/bookmarkname/
---
## FieldSet.BookmarkName property

الحصول على اسم الإشارة المرجعية أو تعيينه.

```csharp
public string BookmarkName { get; set; }
```

### أمثلة

يوضح كيفية إنشاء نص ذي إشارة مرجعية باستخدام حقل SET ، ثم عرضه في المستند باستخدام حقل REF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

 // اسم النص الذي تم وضع إشارة مرجعية عليه باستخدام حقل SET.
// يشير هذا الحقل إلى "إشارة مرجعية" وليس بنية إشارة مرجعية تظهر داخل النص ، ولكن إلى متغير مسمى.
FieldSet fieldSet = (FieldSet)builder.InsertField(FieldType.FieldSet, false);
fieldSet.BookmarkName = "MyBookmark";
fieldSet.BookmarkText = "Hello world!";
fieldSet.Update();

Assert.AreEqual(" SET  MyBookmark \"Hello world!\"", fieldSet.GetFieldCode());

// الرجوع إلى الإشارة المرجعية بالاسم في حقل REF وعرض محتوياتها.
FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
fieldRef.BookmarkName = "MyBookmark";
fieldRef.Update();

Assert.AreEqual(" REF  MyBookmark", fieldRef.GetFieldCode());
Assert.AreEqual("Hello world!", fieldRef.Result);

doc.Save(ArtifactsDir + "Field.SET.REF.docx");
```

### أنظر أيضا

* class [FieldSet](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldset/)
* المجسم [Aspose.Words](../../../)


