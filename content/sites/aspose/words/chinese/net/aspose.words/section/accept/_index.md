---
title: Section.Accept
second_title: Aspose.Words for .NET API 参考
description: Section 方法. 接受访客
type: docs
weight: 70
url: /zh/net/aspose.words/section/accept/
---
## Section.Accept method

接受访客。

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| visitor | DocumentVisitor | 将访问节点的访问者。 |

### 返回值

如果访问了所有节点，则为真；如果 DocumentVisitor 在访问所有节点之前停止操作，则返回 false。

### 评论

枚举此节点及其所有子节点。每个节点调用 DocumentVisitor 上的相应方法。

有关更多信息，请参阅访问者设计模式。

调用 DocumentVisitor.VisitSectionStart，然后为 section 的所有子节点调用 Accept，最后调用 DocumentVisitor.VisitSectionEnd。

### 也可以看看

* class [DocumentVisitor](../../documentvisitor/)
* class [Section](../)
* 命名空间 [Aspose.Words](../../section/)
* 部件 [Aspose.Words](../../../)


