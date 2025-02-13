---
title: Class UserInformation
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.UserInformation فصل. يحدد معلومات حول المستخدم.
type: docs
weight: 2610
url: /ar/net/aspose.words.fields/userinformation/
---
## UserInformation class

يحدد معلومات حول المستخدم.

```csharp
public class UserInformation
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [UserInformation](userinformation/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| static [DefaultUser](../../aspose.words.fields/userinformation/defaultuser/) { get; } | معلومات المستخدم الافتراضية . |
| [Address](../../aspose.words.fields/userinformation/address/) { get; set; } | الحصول على أو تعيين العنوان البريدي للمستخدم. |
| [Initials](../../aspose.words.fields/userinformation/initials/) { get; set; } | الحصول على أو تعيين الأحرف الأولى للمستخدم. |
| [Name](../../aspose.words.fields/userinformation/name/) { get; set; } | الحصول على أو تحديد اسم المستخدم . |

### أمثلة

يوضح كيفية تعيين تفاصيل المستخدم ، وعرضها باستخدام الحقول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إنشاء كائن معلومات المستخدم وتعيينه كمصدر بيانات للحقول التي تعرض معلومات المستخدم.
UserInformation userInformation = new UserInformation
{
    Name = "John Doe",
    Initials = "J. D.",
    Address = "123 Main Street"
};
doc.FieldOptions.CurrentUser = userInformation;

// أدخل حقول اسم المستخدم والمستخدمين و USERADDRESS التي تعرض قيم
// الخصائص الخاصة بكائن معلومات المستخدم الذي أنشأناه أعلاه. 
Assert.AreEqual(userInformation.Name, builder.InsertField(" USERNAME ").Result);
Assert.AreEqual(userInformation.Initials, builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual(userInformation.Address, builder.InsertField(" USERADDRESS ").Result);

// يحتوي كائن خيارات الحقل أيضًا على مستخدم افتراضي ثابت يمكن أن تشير إليه الحقول من جميع المستندات.
UserInformation.DefaultUser.Name = "Default User";
UserInformation.DefaultUser.Initials = "D. U.";
UserInformation.DefaultUser.Address = "One Microsoft Way";
doc.FieldOptions.CurrentUser = UserInformation.DefaultUser;

Assert.AreEqual("Default User", builder.InsertField(" USERNAME ").Result);
Assert.AreEqual("D. U.", builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual("One Microsoft Way", builder.InsertField(" USERADDRESS ").Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.CurrentUser.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


