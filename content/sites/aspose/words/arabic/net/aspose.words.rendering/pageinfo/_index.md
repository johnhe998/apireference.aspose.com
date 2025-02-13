---
title: Class PageInfo
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Rendering.PageInfo فصل. يمثل معلومات حول صفحة وثيقة معينة.
type: docs
weight: 4310
url: /ar/net/aspose.words.rendering/pageinfo/
---
## PageInfo class

يمثل معلومات حول صفحة وثيقة معينة.

```csharp
public class PageInfo
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [HeightInPoints](../../aspose.words.rendering/pageinfo/heightinpoints/) { get; } | الحصول على ارتفاع الصفحة بالنقاط . |
| [Landscape](../../aspose.words.rendering/pageinfo/landscape/) { get; } | إرجاع صحيح إذا كان اتجاه الصفحة المحدد في المستند لهذه الصفحة أفقيًا. |
| [PaperSize](../../aspose.words.rendering/pageinfo/papersize/) { get; } | الحصول على حجم الورق كتعداد . |
| [PaperTray](../../aspose.words.rendering/pageinfo/papertray/) { get; } | الحصول على درج (حاوية) الورق لهذه الصفحة كما هو محدد في المستند. |
| [SizeInPoints](../../aspose.words.rendering/pageinfo/sizeinpoints/) { get; } | الحصول على حجم الصفحة بالنقاط . |
| [WidthInPoints](../../aspose.words.rendering/pageinfo/widthinpoints/) { get; } | الحصول على عرض الصفحة بالنقاط . |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetDotNetPaperSize](../../aspose.words.rendering/pageinfo/getdotnetpapersize/)(PaperSizeCollection) | يحصل على ملفPaperSize كائن مناسب للطباعة الصفحة التي يمثلها هذا`PageInfo` . |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels)(float, float) | حساب حجم الصفحة بالبكسل لعامل تكبير ودقة محددين. |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels_1)(float, float, float) | حساب حجم الصفحة بالبكسل لعامل تكبير ودقة محددين. |
| [GetSpecifiedPrinterPaperSource](../../aspose.words.rendering/pageinfo/getspecifiedprinterpapersource/)(PaperSourceCollection, PaperSource) | يحصل على ملفPaperSource كائن مناسب للطباعة الصفحة التي يمثلها هذا`PageInfo` . |

### ملاحظات

يمثل عرض الصفحة وارتفاعها الناتج عن هذا الكائن الحجم "النهائي" للصفحة ، على سبيل المثال ، تم تدويرهما بالفعل إلى الاتجاه الصحيح.

### أمثلة

يوضح كيفية طباعة حجم الصفحة ومعلومات الاتجاه لكل صفحة في مستند Word.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// يحتوي القسم الأول على صفحتين. سنقوم بتعيين درج ورق طابعة مختلف لكل واحد ،
// الذي سيتطابق رقمه مع نوع مصدر الورق. هذه المصادر وأنواعها سوف تختلف
// اعتمادًا على برنامج تشغيل الطابعة المثبت.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // تحتوي كل صفحة على كائن PageInfo ، والفهرس الخاص به هو رقم الصفحة المعنية.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // اطبع اتجاه الصفحة وأبعادها.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // اطبع معلومات علبة المصدر.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Rendering](../../aspose.words.rendering/)
* المجسم [Aspose.Words](../../)


