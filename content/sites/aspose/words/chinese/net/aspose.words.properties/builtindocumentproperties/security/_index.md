---
title: BuiltInDocumentProperties.Security
second_title: Aspose.Words for .NET API 参考
description: BuiltInDocumentProperties 财产. 将文档的安全级别指定为数值
type: docs
weight: 250
url: /zh/net/aspose.words.properties/builtindocumentproperties/security/
---
## BuiltInDocumentProperties.Security property

将文档的安全级别指定为数值。

```csharp
public DocumentSecurity Security { get; set; }
```

### 评论

此属性仅用于提供信息，因为 Microsoft Word 并不总是 设置此属性。此属性仅在 DOC 和 OOXML 文档中可用。

要保护或取消保护文档，请使用 [`Protect`](../../../aspose.words/document/protect/)和[`Unprotect`](../../../aspose.words/document/unprotect/)方法。

Aspose.Words 在保存文档之前将此属性更新为正确的值。

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

* enum [DocumentSecurity](../../documentsecurity/)
* class [BuiltInDocumentProperties](../)
* 命名空间 [Aspose.Words.Properties](../../builtindocumentproperties/)
* 部件 [Aspose.Words](../../../)


