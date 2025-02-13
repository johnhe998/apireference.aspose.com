---
title: StructuredDocumentTag.Style
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag ملكية. الحصول على أو تحديد نمط علامة المستند المهيكلة.
type: docs
weight: 260
url: /ar/net/aspose.words.markup/structureddocumenttag/style/
---
## StructuredDocumentTag.Style property

الحصول على أو تحديد نمط علامة المستند المهيكلة.

```csharp
public Style Style { get; set; }
```

### ملاحظات

فقطCharacter نمط أوParagraph يمكن ضبط النمط بنمط الحرف المرتبط.

### أمثلة

يوضح كيفية العمل باستخدام أنماط عناصر التحكم في المحتوى.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي طريقتان لتطبيق نمط من المستند إلى علامة مستند منظم.
// 1 - تطبيق كائن نمط من مجموعة أنماط المستند:
Style quoteStyle = doc.Styles[StyleIdentifier.Quote];
StructuredDocumentTag sdtPlainText =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline) { Style = quoteStyle };

// 2 - الإشارة إلى نمط في المستند بالاسم:
StructuredDocumentTag sdtRichText =
    new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Inline) { StyleName = "Quote" };

builder.InsertNode(sdtPlainText);
builder.InsertNode(sdtRichText);

Assert.AreEqual(NodeType.StructuredDocumentTag, sdtPlainText.NodeType);

NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true);

foreach (Node node in tags)
{
    StructuredDocumentTag sdt = (StructuredDocumentTag)node;

    Assert.AreEqual(StyleIdentifier.Quote, sdt.Style.StyleIdentifier);
    Assert.AreEqual("Quote", sdt.StyleName);
}
```

### أنظر أيضا

* class [Style](../../../aspose.words/style/)
* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


