---
title: Enum PdfCustomPropertiesExport
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfCustomPropertiesExport تعداد. يحدد الطريقCustomDocumentProperties يتم تصديرها إلى ملف PDF .
type: docs
weight: 5140
url: /ar/net/aspose.words.saving/pdfcustompropertiesexport/
---
## PdfCustomPropertiesExport enumeration

يحدد الطريق[`CustomDocumentProperties`](../../aspose.words/document/customdocumentproperties/) يتم تصديرها إلى ملف PDF .

```csharp
public enum PdfCustomPropertiesExport
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | لم يتم تصدير أي خصائص مخصصة. |
| Standard | `1` | يتم تصدير الخصائص المخصصة كمدخلات في / قاموس المعلومات. |
| Metadata | `2` | الخصائص المخصصة هي بيانات وصفية . |

### أمثلة

يوضح كيفية تصدير الخصائص المخصصة أثناء تحويل مستند إلى PDF.

```csharp
Document doc = new Document();

doc.CustomDocumentProperties.Add("Company", "My value");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "CustomPropertiesExport" على "PdfCustomPropertiesExport.None" لتجاهلها
 // خصائص المستند المخصصة لأننا نحفظ المستند إلى .PDF.
// تعيين خاصية "CustomPropertiesExport" على "PdfCustomPropertiesExport.Standard"
// للحفاظ على الخصائص المخصصة داخل مستند PDF الناتج.
// تعيين خاصية "CustomPropertiesExport" على "PdfCustomPropertiesExport.Metadata"
// للحفاظ على الخصائص المخصصة في حزمة XMP.
options.CustomPropertiesExport = pdfCustomPropertiesExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.CustomPropertiesExport.pdf", options);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


