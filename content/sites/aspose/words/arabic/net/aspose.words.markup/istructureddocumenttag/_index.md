---
title: Interface IStructuredDocumentTag
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Markup.IStructuredDocumentTag واجهه المستخدم. واجهة لتعريف البيانات المشتركة لـStructuredDocumentTag وStructuredDocumentTagRangeStart .
type: docs
weight: 3730
url: /ar/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

واجهة لتعريف البيانات المشتركة لـ[`StructuredDocumentTag`](../structureddocumenttag/) و[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/) .

```csharp
public interface IStructuredDocumentTag
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | الحصول على أو تحديد لون علامة المستند المهيكلة. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | يحدد معرّفًا رقميًا فريدًا ومستمرًا للقراءة فقط لهذا الغرض **المعاملة الخاصة والتفضيلية**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | يحدد ما إذا كان محتوى هذا **المعاملة الخاصة والتفضيلية** يجب أن يتم تفسيره على أنه يحتوي على عنصر نائب text (على عكس محتويات النص العادي داخل SDT). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | يحصل على المستوى الذي عنده هذا **المعاملة الخاصة والتفضيلية** يحدث في شجرة الوثيقة. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | عند التعيين على "صواب" ، ستمنع هذه الخاصية المستخدم من حذف ذلك **المعاملة الخاصة والتفضيلية** . |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | عند التعيين على "صواب" ، ستمنع هذه الخاصية المستخدم من تحرير محتويات هذا **المعاملة الخاصة والتفضيلية** . |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | يحصل على ملف[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) يحتوي على نص عنصر نائب يجب عرضه عندما تكون محتويات تشغيل SDT فارغة ، يكون عنصر XML المعين المرتبط فارغًا كما هو محدد عبر[`XmlMapping`](./xmlmapping/) element أو ملف[`IsShowingPlaceholderText`](./isshowingplaceholdertext/) العنصر صحيح. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | يحصل أو يحدد اسم[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) تحتوي على نص عنصر نائب. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | يحصل على نوع من هذا **علامة وثيقة منظم** . |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | يحدد علامة مرتبطة بعقدة SDT الحالية. لا يمكن أن يكون فارغًا . |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | تحديد الاسم المألوف المرتبط بهذا **المعاملة الخاصة والتفضيلية** . لا يمكن أن يكون فارغًا . |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | يحصل على سلسلة تمثل XML الموجود داخل العقدة في ملفFlatOpc التنسيق . |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | الحصول على كائن يمثل تعيين علامة المستند المهيكلة هذه إلى بيانات XML في جزء XML مخصص من المستند الحالي. |

## طُرق

| اسم | وصف |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | إرجاع صحيح إذا كان هذا المثال عبارة عن علامة وثيقة منظمة. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | إرجاع كائن العقدة الذي يقوم بتنفيذ هذه الواجهة. |

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Markup](../../aspose.words.markup/)
* المجسم [Aspose.Words](../../)


