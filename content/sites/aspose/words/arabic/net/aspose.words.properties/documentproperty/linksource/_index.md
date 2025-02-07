---
title: DocumentProperty.LinkSource
second_title: Aspose.Words لمراجع .NET API
description: DocumentProperty ملكية. يحصل على مصدر خاصية الوثيقة المخصصة المرتبطة.
type: docs
weight: 20
url: /ar/net/aspose.words.properties/documentproperty/linksource/
---
## DocumentProperty.LinkSource property

يحصل على مصدر خاصية الوثيقة المخصصة المرتبطة.

```csharp
public string LinkSource { get; }
```

### أمثلة

يوضح كيفية ربط خاصية مستند مخصصة بإشارة مرجعية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("MyBookmark");
builder.Write("Hello world!");
builder.EndBookmark("MyBookmark");

// ربط خاصية مخصصة جديدة بإشارة مرجعية. قيمة هذا العقار
// ستكون محتويات الإشارة المرجعية التي تشير إليها في عضو "LinkSource".
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");

Assert.AreEqual(true, customProperty.IsLinkToContent);
Assert.AreEqual("MyBookmark", customProperty.LinkSource);
Assert.AreEqual("Hello world!", customProperty.Value);

doc.Save(ArtifactsDir + "DocumentProperties.LinkCustomDocumentPropertiesToBookmark.docx");
```

### أنظر أيضا

* class [DocumentProperty](../)
* مساحة الاسم [Aspose.Words.Properties](../../documentproperty/)
* المجسم [Aspose.Words](../../../)


