---
title: RtfLoadOptions.RecognizeUtf8Text
second_title: Aspose.Words لمراجع .NET API
description: RtfLoadOptions ملكية. عند التعيين على صواب CharsetDetectorسيحاول اكتشاف أحرف UTF8  سيتم الاحتفاظ بها أثناء الاستيراد.
type: docs
weight: 20
url: /ar/net/aspose.words.loading/rtfloadoptions/recognizeutf8text/
---
## RtfLoadOptions.RecognizeUtf8Text property

عند التعيين على صواب ،CharsetDetectorسيحاول اكتشاف أحرف UTF8 ، سيتم الاحتفاظ بها أثناء الاستيراد.

القيمة الافتراضية خاطئة .

```csharp
public bool RecognizeUtf8Text { get; set; }
```

### أمثلة

يوضح كيفية اكتشاف أحرف UTF-8 أثناء تحميل مستند RTF.

```csharp
// قم بإنشاء كائن "RtfLoadOptions" لتعديل كيفية تحميل مستند RTF.
RtfLoadOptions loadOptions = new RtfLoadOptions();

// اضبط خاصية "RecognizeUtf8Text" على "false" بافتراض أن المستند يستخدم مجموعة أحرف ISO 8859-1
// ويحمل كل حرف في المستند.
// قم بتعيين خاصية "RecognizeUtf8Text" على "true" لتحليل أي أحرف متغيرة الطول قد تظهر في النص.
loadOptions.RecognizeUtf8Text = recognizeUtf8Text;

Document doc = new Document(MyDir + "UTF-8 characters.rtf", loadOptions);

Assert.AreEqual(
    recognizeUtf8Text
        ? "“John Doe´s list of currency symbols”™\r" +
          "€, ¢, £, ¥, ¤"
        : "â€œJohn DoeÂ´s list of currency symbolsâ€\u009dâ„¢\r" +
          "â‚¬, Â¢, Â£, Â¥, Â¤",
    doc.FirstSection.Body.GetText().Trim());
```

### أنظر أيضا

* class [RtfLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../rtfloadoptions/)
* المجسم [Aspose.Words](../../../)


