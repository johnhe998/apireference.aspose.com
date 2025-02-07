---
title: Document.ProtectionType
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取当前活动的文档保护类型
type: docs
weight: 310
url: /zh/net/aspose.words/document/protectiontype/
---
## Document.ProtectionType property

获取当前活动的文档保护类型。

```csharp
public ProtectionType ProtectionType { get; }
```

### 评论

此属性允许检索当前设置的文档保护类型。 要更改文档保护类型，请使用[`Protect`](../protect/) 和[`Unprotect`](../unprotect/)方法。

当文档受到保护时，用户只能进行有限的更改， ，例如添加注释、进行修订或填写表格。

请注意，文档保护不同于写保护。 写保护是使用[`WriteProtection`](../writeprotection/)

### 例子

显示如何保护和取消保护文档。

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 如果我们使用 Microsoft Word 打开此文档并打算对其进行编辑，
// 我们需要应用密码才能通过保护。
doc.Save(ArtifactsDir + "Document.Protect.docx");

// 请注意，该保护仅适用于打开我们文档的 Microsoft Word 用户。
// 我们没有以任何方式加密文档，我们不需要密码以编程方式打开和编辑它。
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// 有两种方法可以从文档中删除保护。
// 1 - 没有密码：
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - 使用正确的密码：
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### 也可以看看

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


