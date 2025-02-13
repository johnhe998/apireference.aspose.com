---
title: StructuredDocumentTag.Clear
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag طريقة. يمسح محتويات علامة المستند المهيكلة هذه ويعرض عنصرًا نائبًا إذا تم تحديده.
type: docs
weight: 330
url: /ar/net/aspose.words.markup/structureddocumenttag/clear/
---
## StructuredDocumentTag.Clear method

يمسح محتويات علامة المستند المهيكلة هذه ويعرض عنصرًا نائبًا إذا تم تحديده.

```csharp
public void Clear()
```

### ملاحظات

لا يمكن مسح محتويات علامة مستند منظم إذا كانت بها مراجعات.

إذا تم تعيين علامة المستند المهيكلة هذه إلى XML المخصص (باستخدام امتداد[`XmlMapping`](../xmlmapping/) ) ، تم مسح عقدة XML المشار إليها.

### أمثلة

يوضح كيفية حذف محتويات عناصر علامة المستند المهيكلة.

```csharp
Document doc = new Document();

// إنشاء علامة مستند منظم بنص عادي ، ثم إلحاقه بالمستند.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// علامة المستند المهيكلة هذه ، والتي تكون في شكل مربع نص ، تعرض بالفعل نص العنصر النائب.
Assert.AreEqual("Click here to enter text.", tag.GetText().Trim());
Assert.True(tag.IsShowingPlaceholderText);

// إنشاء كتلة إنشاء بمحتويات نصية.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;
BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "My placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.EnsureMinimum();
substituteBlock.FirstSection.Body.FirstParagraph.AppendChild(new Run(glossaryDoc, "Custom placeholder text."));
glossaryDoc.AppendChild(substituteBlock);

// قم بتعيين خاصية "PlaceholderName" الخاصة بعلامة المستند المهيكلة على اسم الكتلة البرمجية الإنشائية للحصول عليها
// علامة المستند المهيكلة لعرض محتويات الكتلة البرمجية الإنشائية بدلاً من النص الافتراضي الأصلي.
tag.PlaceholderName = "My placeholder";

Assert.AreEqual("Custom placeholder text.", tag.GetText().Trim());
Assert.True(tag.IsShowingPlaceholderText);

// قم بتحرير نص علامة المستند المهيكلة وإخفاء نص العنصر النائب.
Run run = (Run)tag.GetChild(NodeType.Run, 0, true);
run.Text = "New text.";
tag.IsShowingPlaceholderText = false;

Assert.AreEqual("New text.", tag.GetText().Trim());

// استخدم طريقة "Clear" لمسح محتويات علامة المستند المنظمة هذه وعرض العنصر النائب مرة أخرى.
tag.Clear();

Assert.True(tag.IsShowingPlaceholderText);
Assert.AreEqual("Custom placeholder text.", tag.GetText().Trim());
```

### أنظر أيضا

* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


