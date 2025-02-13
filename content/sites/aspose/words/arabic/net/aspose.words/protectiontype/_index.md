---
title: Enum ProtectionType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ProtectionType تعداد. نوع الحماية للمستند .
type: docs
weight: 4260
url: /ar/net/aspose.words/protectiontype/
---
## ProtectionType enumeration

نوع الحماية للمستند .

```csharp
public enum ProtectionType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| AllowOnlyComments | `1` | يمكن للمستخدم تعديل التعليقات فقط في المستند. |
| AllowOnlyFormFields | `2` | يمكن للمستخدم إدخال البيانات فقط في حقول النموذج في المستند. |
| AllowOnlyRevisions | `0` | يمكن للمستخدم إضافة علامات المراجعة فقط إلى المستند. |
| ReadOnly | `3` | لا يسمح بإجراء أي تغييرات على المستند. متاح منذ Microsoft Word 2003. |
| NoProtection | `-1` | المستند غير محمي . |

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

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


