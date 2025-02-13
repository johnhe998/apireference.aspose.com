---
title: Enum DocumentSecurity
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Properties.DocumentSecurity 枚举. 用作Securityproperty. 将文档的安全级别指定为数值
type: docs
weight: 4240
url: /zh/net/aspose.words.properties/documentsecurity/
---
## DocumentSecurity enumeration

用作[`Security`](../builtindocumentproperties/security/)property. 将文档的安全级别指定为数值。

```csharp
[Flags]
public enum DocumentSecurity
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 属性没有指定安全状态。 |
| PasswordProtected | `1` | 文档受密码保护。 （到目前为止从未在文档中看到过注释）. |
| ReadOnlyRecommended | `2` | 尽可能以只读方式打开的文档，但可以覆盖设置。 |
| ReadOnlyEnforced | `4` | 始终以只读方式打开的文档。 |
| ReadOnlyExceptAnnotations | `8` | 始终以只读方式打开的文档，注释除外。 |

### 例子

演示如何使用文档属性来显示文档的安全级别。

```csharp
Document doc = new Document();

Assert.AreEqual(DocumentSecurity.None, doc.BuiltInDocumentProperties.Security);

// 如果我们将文档配置为只读，它将使用“安全”内置属性显示此状态。
doc.WriteProtection.ReadOnlyRecommended = true;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyRecommended, 
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx").BuiltInDocumentProperties.Security);

// 对文档进行写保护，然后验证其安全级别。
doc = new Document();

Assert.False(doc.WriteProtection.IsWriteProtected);

doc.WriteProtection.SetPassword("MyPassword");

Assert.True(doc.WriteProtection.ValidatePassword("MyPassword"));
Assert.True(doc.WriteProtection.IsWriteProtected);

doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyEnforced,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx").BuiltInDocumentProperties.Security);

// “安全”是一个描述性属性。我们可以手动编辑它的值。
doc = new Document();

doc.Protect(ProtectionType.AllowOnlyComments, "MyPassword");
doc.BuiltInDocumentProperties.Security = DocumentSecurity.ReadOnlyExceptAnnotations;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyExceptAnnotations,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx").BuiltInDocumentProperties.Security);
```

### 也可以看看

* 命名空间 [Aspose.Words.Properties](../../aspose.words.properties/)
* 部件 [Aspose.Words](../../)


