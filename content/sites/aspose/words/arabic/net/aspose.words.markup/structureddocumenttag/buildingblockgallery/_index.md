---
title: StructuredDocumentTag.BuildingBlockGallery
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTag ملكية. تحديد نوع الكتلة البرمجية الإنشائية لهذا الغرض المعاملة الخاصة والتفضيلية . لا يمكن أن يكون فارغًا .
type: docs
weight: 40
url: /ar/net/aspose.words.markup/structureddocumenttag/buildingblockgallery/
---
## StructuredDocumentTag.BuildingBlockGallery property

تحديد نوع الكتلة البرمجية الإنشائية لهذا الغرض **المعاملة الخاصة والتفضيلية** . لا يمكن أن يكون فارغًا .

```csharp
public string BuildingBlockGallery { get; set; }
```

### ملاحظات

الوصول إلى هذه الخاصية سيعمل فقط من أجلBuildingBlockGallery و DocPartObj أنواع المعاملة الخاصة والتفضيلية. إنه للقراءة فقط لـ **المعاملة الخاصة والتفضيلية**من نوع جزء المستند.

سيحدث استثناء لجميع أنواع المعاملة الخاصة والتفضيلية الأخرى.

### أمثلة

يوضح كيفية إدراج علامة مستند منظم ككتلة إنشاء ، وتعيين فئته ومعرضه.

```csharp
Document doc = new Document();

StructuredDocumentTag buildingBlockSdt =
    new StructuredDocumentTag(doc, SdtType.BuildingBlockGallery, MarkupLevel.Block)
    {
        BuildingBlockCategory = "Built-in",
        BuildingBlockGallery = "Table of Contents"
    };

doc.FirstSection.Body.AppendChild(buildingBlockSdt);

doc.Save(ArtifactsDir + "StructuredDocumentTag.BuildingBlockCategories.docx");
```

### أنظر أيضا

* class [StructuredDocumentTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttag/)
* المجسم [Aspose.Words](../../../)


