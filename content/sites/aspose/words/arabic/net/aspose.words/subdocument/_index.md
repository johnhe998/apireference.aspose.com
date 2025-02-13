---
title: Class SubDocument
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.SubDocument فصل. يمثل أ مستند ثانوي  وهي إشارة إلى مستند مخزن خارجيًا .
type: docs
weight: 5870
url: /ar/net/aspose.words/subdocument/
---
## SubDocument class

يمثل أ **مستند ثانوي** - وهي إشارة إلى مستند مخزن خارجيًا .

```csharp
public class SubDocument : Node
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | يحدد معرف العقدة المخصص . |
| virtual [Document](../../aspose.words/node/document/) { get; } | الحصول على المستند الذي تنتمي إليه هذه العقدة . |
| virtual [IsComposite](../../aspose.words/node/iscomposite/) { get; } | إرجاع صحيح إذا كانت هذه العقدة يمكن أن تحتوي على عقد أخرى. |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | يحصل على العقدة التي تلي هذه العقدة مباشرة. |
| override [NodeType](../../aspose.words/subdocument/nodetype/) { get; } | عوائد **نوع العقد** |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | الحصول على الأصل المباشر لهذه العقدة. |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | يحصل على العقدة التي تسبق هذه العقدة مباشرة. |
| [Range](../../aspose.words/node/range/) { get; } | إرجاع أ **نطاق** الكائن الذي يمثل جزء المستند الموجود في هذه العقدة. |

## طُرق

| اسم | وصف |
| --- | --- |
| override [Accept](../../aspose.words/subdocument/accept/)(DocumentVisitor) | يقبل الزائر . |
| [Clone](../../aspose.words/node/clone/)(bool) | لإنشاء نسخة مكررة من العقدة . |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | يحصل على أول سلف محدد[`NodeType`](../nodetype/) . |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | الحصول على الأصل الأول لنوع الكائن المحدد. |
| virtual [GetText](../../aspose.words/node/gettext/)() | يحصل على نص هذه العقدة وجميع توابعها. |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | الحصول على العقدة التالية وفقًا لخوارزمية اجتياز الشجرة بالطلب المسبق. |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | الحصول على العقدة السابقة وفقًا لخوارزمية اجتياز الشجرة بالطلب المسبق. |
| [Remove](../../aspose.words/node/remove/)() | يزيل نفسه من الأصل. |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | يصدر محتوى العقدة إلى سلسلة بالتنسيق المحدد. |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | يصدر محتوى العقدة إلى سلسلة باستخدام خيارات الحفظ المحددة. |

### ملاحظات

في هذا الإصدار من Aspose.Words ،`SubDocument` العقد لا توفر الأساليب العامة والخصائص لإنشاء مستند ثانوي أو تعديله. في هذا الإصدار ، لا يمكنك إنشاء عقد مستند ثانوي أو تعديل العقد الموجودة باستثناء حذفها.

`SubDocument` يمكن أن يكون فقط تابعًا لـ[`Paragraph`](../paragraph/).

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

* class [Node](../node/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


