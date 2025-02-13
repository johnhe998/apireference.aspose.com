---
title: Class TxtLoadOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Loading.TxtLoadOptions فصل. يسمح بتحديد خيارات إضافية عند التحميلText وثيقة فيDocument الكائن .
type: docs
weight: 3530
url: /ar/net/aspose.words.loading/txtloadoptions/
---
## TxtLoadOptions class

يسمح بتحديد خيارات إضافية عند التحميلText وثيقة في[`Document`](../../aspose.words/document/) الكائن .

```csharp
public class TxtLoadOptions : LoadOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [TxtLoadOptions](txtloadoptions/)() | تهيئة مثيل جديد لهذه الفئة بالقيم الافتراضية. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [BaseUri](../../aspose.words.loading/loadoptions/baseuri/) { get; set; } | الحصول على أو تعيين السلسلة التي سيتم استخدامها لحل URIs النسبية الموجودة في المستند إلى URIs المطلقة عند الحاجة . يمكن أن تكون سلسلة فارغة أو فارغة. الافتراضي هو فارغ. |
| [ConvertMetafilesToPng](../../aspose.words.loading/loadoptions/convertmetafilestopng/) { get; set; } | الحصول على أو تعيين ما إذا كان سيتم تحويل ملف تعريف (Wmf أوEmf ) صور لPng تنسيق الصورة . |
| [ConvertShapeToOfficeMath](../../aspose.words.loading/loadoptions/convertshapetoofficemath/) { get; set; } | الحصول على أو تعيين ما إذا كان سيتم تحويل الأشكال باستخدام EquationXML إلى كائنات Office Math. |
| [DetectNumberingWithWhitespaces](../../aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/) { get; set; } | يسمح بتحديد كيفية التعرف على عناصر القائمة المرقمة عند استيراد المستند من تنسيق نص عادي. القيمة الافتراضية هي true. |
| [DocumentDirection](../../aspose.words.loading/txtloadoptions/documentdirection/) { get; set; } | الحصول على أو تحديد اتجاه المستند. القيمة الافتراضية هيLeftToRight . |
| [Encoding](../../aspose.words.loading/loadoptions/encoding/) { get; set; } | الحصول على أو تعيين الترميز الذي سيتم استخدامه لتحميل مستند HTML أو TXT أو CHM إذا لم يتم تحديد الترميز داخل المستند. يمكن أن يكون فارغًا. الافتراضي هو فارغ. |
| [FlatOpcXmlMappingOnly](../../aspose.words.loading/loadoptions/flatopcxmlmappingonly/) { get; set; } | الحصول على القيمة أو تعيينها لتحديد تنسيقات المستندات التي يُسمح لها بالتعيين[`XmlMapping`](../../aspose.words.markup/structureddocumenttag/xmlmapping/) . بشكل افتراضي فقطFlatOpc يُسمح بتعيين تنسيق المستند. |
| [FontSettings](../../aspose.words.loading/loadoptions/fontsettings/) { get; set; } | يسمح بتحديد إعدادات خط الوثيقة. |
| [LanguagePreferences](../../aspose.words.loading/loadoptions/languagepreferences/) { get; } | الحصول على تفضيلات اللغة التي سيتم استخدامها عند تحميل المستند. |
| [LeadingSpacesOptions](../../aspose.words.loading/txtloadoptions/leadingspacesoptions/) { get; set; } | الحصول على أو تعيين الخيار المفضل لمعالجة المسافة البادئة. القيمة الافتراضية هيConvertToIndent . |
| [LoadFormat](../../aspose.words.loading/loadoptions/loadformat/) { get; set; } | يحدد تنسيق المستند الذي سيتم تحميله. الافتراضي هوAuto . |
| [MswVersion](../../aspose.words.loading/loadoptions/mswversion/) { get; set; } | يسمح بتحديد أن عملية تحميل المستند يجب أن تتطابق مع إصدار MS Word محدد. القيمة الافتراضية هيWord2019 |
| [Password](../../aspose.words.loading/loadoptions/password/) { get; set; } | الحصول على كلمة المرور أو تعيينها لفتح مستند مشفر. يمكن أن تكون سلسلة فارغة أو فارغة. الافتراضي هو فارغ. |
| [PreserveIncludePictureField](../../aspose.words.loading/loadoptions/preserveincludepicturefield/) { get; set; } | الحصول على أو تحديد ما إذا كان سيتم الاحتفاظ بحقل INCLUDEPICTURE عند قراءة تنسيقات Microsoft Word . القيمة الافتراضية هي false . |
| [ProgressCallback](../../aspose.words.loading/loadoptions/progresscallback/) { get; set; } | يتم الاتصال به أثناء تحميل مستند ويقبل البيانات حول تقدم التحميل. |
| [ResourceLoadingCallback](../../aspose.words.loading/loadoptions/resourceloadingcallback/) { get; set; } | يسمح بالتحكم في كيفية تحميل الموارد الخارجية (الصور ، أوراق الأنماط) عند استيراد مستند من HTML ، MHTML. |
| [TempFolder](../../aspose.words.loading/loadoptions/tempfolder/) { get; set; } | يسمح باستخدام الملفات المؤقتة عند قراءة المستند. افتراضيًا ، هذه الخاصية هي`لا شيء` ولا يتم استخدام أي ملفات مؤقتة. |
| [TrailingSpacesOptions](../../aspose.words.loading/txtloadoptions/trailingspacesoptions/) { get; set; } | الحصول على أو تعيين الخيار المفضل لمعالجة مساحة زائدة . القيمة الافتراضية هيTrim . |
| [UpdateDirtyFields](../../aspose.words.loading/loadoptions/updatedirtyfields/) { get; set; } | يحدد ما إذا كان سيتم تحديث الحقول بامتداد`متسخ` السمة . |
| [WarningCallback](../../aspose.words.loading/loadoptions/warningcallback/) { get; set; } | تم الاستدعاء أثناء عملية التحميل ، عند اكتشاف مشكلة قد تؤدي إلى فقدان دقة البيانات أو التنسيق. |

### أنظر أيضا

* class [LoadOptions](../loadoptions/)
* مساحة الاسم [Aspose.Words.Loading](../../aspose.words.loading/)
* المجسم [Aspose.Words](../../)


