---
title: شطب الكلمات
linktitle: شطب الكلمات
second_title: Aspose.PDF لمرجع .NET API
description: تقدم هذه المقالة دليلاً مفصلاً خطوة بخطوة لاستخدام ميزة Aspose.PDF لـ .NET's Strike Out Words ، بما في ذلك دليل خطوة بخطوة وشروحات
type: docs
weight: 150
url: /ar/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET هي مكتبة لمعالجة مستندات PDF ومعالجتها توفر ميزات متنوعة لإنشاء ملفات PDF وتعديلها وتحويلها. إحدى الميزات المفيدة التي يوفرها Aspose.PDF هي القدرة على شطب الكلمات أو العبارات في مستند PDF باستخدام الكود المصدري C #. في هذه المقالة ، سوف نقدم دليلًا تفصيليًا حول كيفية كتابة الكلمات باستخدام Aspose.PDF لـ .NET.

## تحميل وثيقة PDF
الخطوة الأولى هي تحميل مستند PDF الذي تريد تعديله. في هذا البرنامج التعليمي ، سنقوم بتحميل مستند PDF باسم "input.pdf" من مجلد "YOUR DOCUMENT DIRECTORY". 

```
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## البحث عن أجزاء النص
لشطب كلمات أو عبارات معينة في مستند PDF ، تحتاج أولاً إلى البحث عنها. يوفر Aspose.PDF فئة TextFragmentAbsorber التي يمكن استخدامها للبحث عن جزء نص معين في مستند PDF.

```
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

في الكود أعلاه ، نبحث عن جزء النص "Estoque" في مستند PDF. يمكنك تعديل هذا للبحث عن أي كلمة أو عبارة أخرى تريد حذفها.

## شطب أجزاء النص
بعد العثور على أجزاء النص ، فإن الخطوة التالية هي شطبها. يوفر Aspose.PDF فئة StrikeOutAnnotation التي يمكن استخدامها لإنشاء تعليق توضيحي مشطوب لجزء النص. 

```
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

في الكود أعلاه ، نقوم بإنشاء تعليق توضيحي مشطوب لكل جزء نص وجدناه. نحن أيضًا نضع التعتيم والحدود ولون التعليق التوضيحي المشطوب.

## حفظ وثيقة PDF المعدلة
بعد شطب أجزاء النص ، احفظ المستند المعدل.

```
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### مثال على شفرة المصدر لـ Strike Out Words باستخدام Aspose.PDF لـ .NET


```csharp

            
            
            // المسار إلى دليل المستندات.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // افتح المستند
            Document document = new Document(dataDir + "input.pdf");

            // إنشاء مثيل TextFragment Absorber للبحث في جزء نص معين
            Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
            // كرر خلال صفحات مستند PDF
            for (int i = 1; i <= document.Pages.Count; i++)
            {
                // احصل على الصفحة الأولى من مستند PDF
                Page page = document.Pages[1];
                page.Accept(textFragmentAbsorber);
            }

            // قم بإنشاء مجموعة من النص الذي تم امتصاصه
            Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

            // كرر على المجموعة أعلاه
            for (int j = 1; j <= textFragmentCollection.Count; j++)
            {
                Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

                // احصل على أبعاد مستطيلة لكائن TextFragment
                Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
                            (float)textFragment.Position.XIndent,
                            (float)textFragment.Position.YIndent,
                            (float)textFragment.Position.XIndent +
                            (float)textFragment.Rectangle.Width,
                            (float)textFragment.Position.YIndent +
                            (float)textFragment.Rectangle.Height);

                // إنشاء مثيل StrikeOut Annotation
                StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
                // ضبط التعتيم على التعليق التوضيحي
                strikeOut.Opacity = .80f;
                // عيّن الحد لمثيل التعليق التوضيحي
                strikeOut.Border = new Border(strikeOut);
                // اضبط لون التعليق التوضيحي
                strikeOut.Color = Aspose.Pdf.Color.Red;
                // أضف تعليقًا توضيحيًا إلى مجموعة التعليقات التوضيحية الخاصة بـ TextFragment
                textFragment.Page.Annotations.Add(strikeOut);
            }
            dataDir = dataDir + "StrikeOutWords_out.pdf";
            document.Save(dataDir);


        
```
