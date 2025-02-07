---
title: SubDocument.NodeType
second_title: Aspose.Words لمراجع .NET API
description: SubDocument ملكية. عوائد نوع العقد
type: docs
weight: 10
url: /ar/net/aspose.words/subdocument/nodetype/
---
## SubDocument.NodeType property

عوائد **نوع العقد**

```csharp
public override NodeType NodeType { get; }
```

### أمثلة

يوضح كيفية الوصول إلى مستند ثانوي للمستند الرئيسي.

```csharp
Document doc = new Document(MyDir + "Master document.docx");

NodeCollection subDocuments = doc.GetChildNodes(NodeType.SubDocument, true);
// تعمل هذه العقدة كمرجع إلى مستند خارجي ، ولا يمكن الوصول إلى محتوياته.
SubDocument subDocument = (SubDocument)subDocuments[0];

Assert.False(subDocument.IsComposite);
```

### أنظر أيضا

* enum [NodeType](../../nodetype/)
* class [SubDocument](../)
* مساحة الاسم [Aspose.Words](../../subdocument/)
* المجسم [Aspose.Words](../../../)


