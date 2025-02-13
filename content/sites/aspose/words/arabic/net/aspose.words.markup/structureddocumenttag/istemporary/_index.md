---
title: StructuredDocumentTag.IsTemporary
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag ملكية. يحدد ما إذا كان هذا المعاملة الخاصة والتفضيلية يجب إزالتها من مستند WordProcessingML عندما يتم تعديل محتوياته .
type: docs
weight: 160
url: /ar/net/aspose.words.markup/structureddocumenttag/istemporary/
---
## StructuredDocumentTag.IsTemporary property

يحدد ما إذا كان هذا **المعاملة الخاصة والتفضيلية** يجب إزالتها من مستند WordProcessingML عندما يتم تعديل محتوياته .

```csharp
public bool IsTemporary { get; set; }
```

### أمثلة

يوضح كيفية عمل عناصر تحكم ذات استخدام واحد.

```csharp
Document doc = new Document();

// إدراج علامة مستند منظم بنص عادي ،
// الذي سيعمل كنموذج نص عادي يمكن للمستخدم إدخال نص فيه.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// عيّن الخاصية "IsTporary" إلى "true" لجعل علامة المستند المهيكلة تختفي و
// استيعاب محتوياته في المستند بعد أن يقوم المستخدم بتحريره مرة واحدة في Microsoft Word.
// اضبط الخاصية "IsTporary" على "false" للسماح للمستخدم بتحرير المحتويات
// من علامة المستند المهيكل أي عدد من المرات.
tag.IsTemporary = isTemporary;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Please enter text: ");
builder.InsertNode(tag);

// أدخل علامة مستند مهيكلة أخرى في شكل مربع اختيار وقم بتعيين حالتها الافتراضية على "محدد".
tag = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
tag.Checked = true;

// عيّن الخاصية "IsTporary" إلى "true" لجعل خانة الاختيار رمزًا
// بمجرد أن ينقر المستخدم عليها في Microsoft Word.
// اضبط الخاصية "IsTporary" على "false" للسماح للمستخدم بالنقر فوق خانة الاختيار في أي عدد من المرات.
tag.IsTemporary = isTemporary;

builder.Write("\nPlease click the check box: ");
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.IsTemporary.docx");
```

### أنظر أيضا

* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


