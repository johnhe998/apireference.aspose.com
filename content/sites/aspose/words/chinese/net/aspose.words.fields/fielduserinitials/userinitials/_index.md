---
title: FieldUserInitials.UserInitials
second_title: Aspose.Words for .NET API 参考
description: FieldUserInitials 财产. 获取或设置当前用户的姓名缩写
type: docs
weight: 20
url: /zh/net/aspose.words.fields/fielduserinitials/userinitials/
---
## FieldUserInitials.UserInitials property

获取或设置当前用户的姓名缩写。

```csharp
public string UserInitials { get; set; }
```

### 例子

显示如何使用 USERINITIALS 字段。

```csharp
Document doc = new Document();

// 创建一个 UserInformation 对象并将其设置为我们创建的任何字段的用户信息源。
UserInformation userInformation = new UserInformation();
userInformation.Initials = "J. D.";
doc.FieldOptions.CurrentUser = userInformation;

// 创建一个 USERINITIALS 字段来显示当前用户的姓名缩写，
// 取自我们在上面创建的 UserInformation 对象。
DocumentBuilder builder = new DocumentBuilder(doc);
FieldUserInitials fieldUserInitials = (FieldUserInitials)builder.InsertField(FieldType.FieldUserInitials, true);
Assert.AreEqual(userInformation.Initials, fieldUserInitials.Result);

Assert.AreEqual(" USERINITIALS ", fieldUserInitials.GetFieldCode());
Assert.AreEqual("J. D.", fieldUserInitials.Result);

 // 我们可以设置这个属性来让我们的字段覆盖当前存储在 UserInformation 对象中的值。
fieldUserInitials.UserInitials = "J. C.";
fieldUserInitials.Update();

Assert.AreEqual(" USERINITIALS  \"J. C.\"", fieldUserInitials.GetFieldCode());
Assert.AreEqual("J. C.", fieldUserInitials.Result);

// 这不会影响 UserInformation 对象中的值。
Assert.AreEqual("J. D.", doc.FieldOptions.CurrentUser.Initials);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.USERINITIALS.docx");
```

### 也可以看看

* class [FieldUserInitials](../)
* 命名空间 [Aspose.Words.Fields](../../fielduserinitials/)
* 部件 [Aspose.Words](../../../)


