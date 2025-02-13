---
title: Document.Protect
second_title: Aspose.Words لمراجع .NET API
description: Document طريقة. يحمي المستند من التغييرات بدون تغيير كلمة المرور الحالية أو تخصيص كلمة مرور عشوائية.
type: docs
weight: 630
url: /ar/net/aspose.words/document/protect/
---
## Protect(ProtectionType) {#protect}

يحمي المستند من التغييرات بدون تغيير كلمة المرور الحالية أو تخصيص كلمة مرور عشوائية.

```csharp
public void Protect(ProtectionType type)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| type | ProtectionType | يحدد نوع الحماية للمستند. |

### ملاحظات

عندما يكون المستند محميًا ، يمكن للمستخدم إجراء تغييرات محدودة فقط ، مثل إضافة التعليقات التوضيحية أو إجراء المراجعات أو إكمال نموذج.

عندما تقوم بحماية مستند ، وكان المستند يحتوي بالفعل على كلمة مرور حماية ، لا يتم تغيير كلمة مرور الحماية الحالية.

عندما تحمي مستندًا ، ولا يحتوي المستند على كلمة مرور للحماية ، تقوم هذه الطريقة بتعيين كلمة مرور عشوائية تجعل من المستحيل إلغاء حماية المستند في Microsoft Word ، ولكن لا يزال بإمكانك إلغاء حماية المستند في Aspose.Words لأنه لا تتطلب كلمة مرور عند إلغاء الحماية.

### أمثلة

يوضح كيفية إيقاف تشغيل الحماية لأحد الأقسام.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// تطبيق الحماية ضد الكتابة على كل قسم في المستند.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// قم بإيقاف تشغيل الحماية ضد الكتابة للقسم الأول.
doc.Sections[0].ProtectedForForms = false;

// في هذا المستند الناتج ، سنتمكن من تحرير القسم الأول بحرية ،
// وسنكون قادرين فقط على تحرير محتويات حقل النموذج في القسم الثاني.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### أنظر أيضا

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)

---

## Protect(ProtectionType, string) {#protect_1}

يحمي المستند من التغييرات ويعين اختياريًا كلمة مرور للحماية.

```csharp
public void Protect(ProtectionType type, string password)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| type | ProtectionType | يحدد نوع الحماية للمستند. |
| password | String | كلمة المرور لحماية المستند باستخدام . حدد سلسلة فارغة أو فارغة إذا كنت تريد حماية المستند بدون كلمة مرور. |

### ملاحظات

عندما يكون المستند محميًا ، يمكن للمستخدم إجراء تغييرات محدودة فقط ، مثل إضافة التعليقات التوضيحية أو إجراء المراجعات أو إكمال نموذج.

لاحظ أن حماية المستند تختلف عن الحماية ضد الكتابة. يتم تحديد الحماية ضد الكتابة باستخدام امتداد[`WriteProtection`](../writeprotection/).

### أمثلة

يوضح كيفية حماية مستند وإلغاء حمايته.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// إذا فتحنا هذا المستند مع Microsoft Word يعتزم تحريره ،
// سنحتاج إلى تطبيق كلمة المرور لتجاوز الحماية.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// لاحظ أن الحماية تنطبق فقط على مستخدمي Microsoft Word الذين يفتحون وثيقتنا.
// لم نشفر المستند بأي شكل من الأشكال ، ولسنا بحاجة إلى كلمة المرور لفتحه وتعديله برمجيًا.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// هناك طريقتان لإزالة الحماية من المستند.
// 1 - بدون كلمة مرور:
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - بكلمة المرور الصحيحة:
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### أنظر أيضا

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


