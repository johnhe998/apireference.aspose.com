---
title: Field.Unlink
second_title: Aspose.Words لمراجع .NET API
description: Field طريقة. يقوم بإلغاء ربط الحقل.
type: docs
weight: 130
url: /ar/net/aspose.words.fields/field/unlink/
---
## Field.Unlink method

يقوم بإلغاء ربط الحقل.

```csharp
public bool Unlink()
```

### قيمة الإرجاع

`حقيقي` إذا تم إلغاء ربط الحقل ، وإلا`خاطئة` .

### ملاحظات

يستبدل الحقل بأحدث نتيجة له.

لا يمكن إلغاء ربط بعض الحقول ، مثل حقول XE (إدخال الفهرس) وحقول SEQ (التسلسل).

### أمثلة

يوضح كيفية فك ارتباط حقل.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
doc.Range.Fields[1].Unlink();
```

### أنظر أيضا

* class [Field](../)
* مساحة الاسم [Aspose.Words.Fields](../../field/)
* المجسم [Aspose.Words](../../../)


