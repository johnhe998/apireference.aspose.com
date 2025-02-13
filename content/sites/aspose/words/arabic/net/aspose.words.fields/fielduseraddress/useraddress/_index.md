---
title: FieldUserAddress.UserAddress
second_title: Aspose.Words لمراجع .NET API
description: FieldUserAddress ملكية. الحصول على أو تعيين العنوان البريدي للمستخدم الحالي.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fielduseraddress/useraddress/
---
## FieldUserAddress.UserAddress property

الحصول على أو تعيين العنوان البريدي للمستخدم الحالي.

```csharp
public string UserAddress { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقل USERADDRESS.

```csharp
Document doc = new Document();

// إنشاء كائن معلومات المستخدم وتعيينه كمصدر لمعلومات المستخدم لأي حقول نقوم بإنشائها.
UserInformation userInformation = new UserInformation();
userInformation.Address = "123 Main Street";
doc.FieldOptions.CurrentUser = userInformation;

// إنشاء حقل USERADDRESS لعرض عنوان المستخدم الحالي ،
// مأخوذ من كائن معلومات المستخدم الذي أنشأناه أعلاه.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserAddress fieldUserAddress = (FieldUserAddress)builder.InsertField(FieldType.FieldUserAddress, true);
Assert.AreEqual(" USERADDRESS ", fieldUserAddress.GetFieldCode());
Assert.AreEqual("123 Main Street", fieldUserAddress.Result);

 // يمكننا تعيين هذه الخاصية لجعل حقلنا يتجاوز القيمة المخزنة حاليًا في كائن معلومات المستخدم.
fieldUserAddress.UserAddress = "456 North Road";
fieldUserAddress.Update();

Assert.AreEqual(" USERADDRESS  \"456 North Road\"", fieldUserAddress.GetFieldCode());
Assert.AreEqual("456 North Road", fieldUserAddress.Result);

// هذا لا يؤثر على القيمة الموجودة في كائن معلومات المستخدم.
Assert.AreEqual("123 Main Street", doc.FieldOptions.CurrentUser.Address);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERADDRESS.docx");
```

### أنظر أيضا

* class [FieldUserAddress](../)
* مساحة الاسم [Aspose.Words.Fields](../../fielduseraddress/)
* المجسم [Aspose.Words](../../../)


