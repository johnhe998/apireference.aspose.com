---
title: Enum DocumentSplitCriteria
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.DocumentSplitCriteria تعداد. يحدد كيفية تقسيم المستند إلى أجزاء عند الحفظHtml أوEpub التنسيق .
type: docs
weight: 4700
url: /ar/net/aspose.words.saving/documentsplitcriteria/
---
## DocumentSplitCriteria enumeration

يحدد كيفية تقسيم المستند إلى أجزاء عند الحفظHtml أوEpub التنسيق .

```csharp
[Flags]
public enum DocumentSplitCriteria
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | لم يتم تقسيم المستند. |
| PageBreak | `1` | يتم تقسيم المستند إلى أجزاء عند فواصل الصفحات الصريحة . يمكن تحديد فاصل صفحة بواسطة[`PageBreak`](../../aspose.words/controlchar/pagebreak/) ، فاصل مقطعي يحدد بداية قسم جديد في صفحة جديدة ، أو فقرة بها[`PageBreakBefore`](../../aspose.words/paragraphformat/pagebreakbefore/) تعيين الخاصية إلى`حقيقي` . |
| ColumnBreak | `2` | يتم تقسيم المستند إلى أجزاء عند فواصل الأعمدة . يمكن تحديد فاصل عمود بواسطة[`ColumnBreak`](../../aspose.words/controlchar/columnbreak/) حرف or فاصل مقطع يحدد بداية قسم جديد في عمود جديد. |
| SectionBreak | `4` | يتم تقسيم المستند إلى أجزاء عند فاصل مقطعي من أي نوع. |
| HeadingParagraph | `8` | يتم تقسيم المستند إلى أجزاء بتنسيق فقرة باستخدام نمط عنوان **عنوان 1** و **العنوان 2** إلخ استخدم مع[`DocumentSplitHeadingLevel`](../htmlsaveoptions/documentsplitheadinglevel/) لتحديد مستويات العنوان (من 1 إلى المستوى المحدد) ليتم تقسيمها . |

### ملاحظات

`DocumentSplitCriteria`هي مجموعة من الأعلام التي يمكن دمجها. على سبيل المثال ، يمكنك تقسيم document عند فواصل الصفحات وفقرات العناوين في نفس عملية التصدير.

يمكن أن تتداخل المعايير المختلفة جزئيًا. على سبيل المثال، **عنوان 1** يتم إعطاء النمط بشكل متكرر [`PageBreakBefore`](../../aspose.words/paragraphformat/pagebreakbefore/) الملكية لذا فهي تندرج تحت معيارين:PageBreak و HeadingParagraph. يمكن أن تتسبب بعض فواصل المقاطع في حدوث فواصل للصفحات وما إلى ذلك. في الحالات النموذجية ، يكون تحديد علامة واحدة فقط هو الخيار الأكثر عملية.

### أمثلة

يوضح كيفية استخدام ترميز معين عند حفظ مستند في epub.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// استخدم كائن SaveOptions لتحديد ترميز المستند الذي سنقوم بحفظه.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// بشكل افتراضي ، سيكون لمستند الإخراج .epub جميع محتوياته في جزء HTML واحد.
// يسمح لنا معيار الانقسام بتقسيم المستند إلى عدة أجزاء بتنسيق HTML.
// سنضع المعايير لتقسيم الوثيقة إلى فقرات عنوان.
// هذا مفيد للقراء الذين لا يستطيعون قراءة ملفات HTML أكثر من حجم معين.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// حدد أننا نريد تصدير خصائص المستند.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


