---
title: BuiltInDocumentProperties.CharactersWithSpaces
second_title: Aspose.Words لمراجع .NET API
description: BuiltInDocumentProperties ملكية. يمثل تقديرًا لعدد الأحرف بما في ذلك المسافات في المستند.
type: docs
weight: 50
url: /ar/net/aspose.words.properties/builtindocumentproperties/characterswithspaces/
---
## BuiltInDocumentProperties.CharactersWithSpaces property

يمثل تقديرًا لعدد الأحرف (بما في ذلك المسافات) في المستند.

```csharp
public int CharactersWithSpaces { get; set; }
```

### ملاحظات

يقوم Aspose.Words بتحديث هذه الخاصية عندما تتصل[`UpdateWordCount`](../../../aspose.words/document/updatewordcount/).

### أمثلة

يوضح كيفية التعامل مع خصائص المستند في فئة "المحتوى".

```csharp
public void Content()
{
    Document doc = new Document(MyDir + "Paragraphs.docx");
    BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

    // باستخدام الخصائص المضمنة ،
    // يمكننا التعامل مع إحصائيات المستند مثل عدد الكلمات / الصفحة / الأحرف على أنها بيانات وصفية يمكن إلقاء نظرة خاطفة عليها دون فتح المستند
    // يتم الوصول إلى هذه الخصائص عن طريق النقر بزر الماوس الأيمن فوق الملف في Windows Explorer والانتقال إلى Properties > التفاصيل و GT. محتوى
    // إذا أردنا عرض هذه البيانات داخل المستند ، فيمكننا استخدام حقول مثل NUMPAGES و NUMWORDS و NUMCHARS وما إلى ذلك.
    // أيضًا ، يمكن أيضًا عرض هذه القيم في Microsoft Word من خلال التنقل في File > خصائص و GT. خصائص متقدمة >. إحصائيات
    // عدد الصفحات: تعرض خاصية PageCount عدد الصفحات في الوقت الفعلي ويمكن تخصيص قيمتها لخاصية الصفحات

    // تخزن خاصية "الصفحات" عدد صفحات المستند. 
    Assert.AreEqual(6, properties.Pages);

    // تعرض الخصائص المضمنة في "Words" و "Characters" و "CharactersWithSpaces" أيضًا إحصاءات المستندات المختلفة ،
    // ولكننا نحتاج إلى استدعاء طريقة "UpdateWordCount" في المستند بأكمله قبل أن نتوقع أن تحتوي على قيم دقيقة.
    doc.UpdateWordCount();

    Assert.AreEqual(1035, properties.Words);
    Assert.AreEqual(6026, properties.Characters);
    Assert.AreEqual(7041, properties.CharactersWithSpaces);

    // عد عدد الأسطر في المستند ، ثم قم بتعيين النتيجة إلى خاصية "الخطوط" المضمنة.
    LineCounter lineCounter = new LineCounter(doc);
    properties.Lines = lineCounter.GetLineCount();

    Assert.AreEqual(142, properties.Lines);

    // تعيين عدد عقد الفقرة في المستند إلى خاصية "الفقرات" المضمنة.
    properties.Paragraphs = doc.GetChildNodes(NodeType.Paragraph, true).Count;
    Assert.AreEqual(29, properties.Paragraphs);

    // احصل على تقدير لحجم ملف وثيقتنا عبر خاصية "بايت" المضمنة.
    Assert.AreEqual(20310, properties.Bytes);

    // قم بتعيين قالب مختلف للمستند الخاص بنا ، ثم قم بتحديث الخاصية المضمنة في "القالب" يدويًا لتعكس هذا التغيير.
    doc.AttachedTemplate = MyDir + "Business brochure.dotx";

    Assert.AreEqual("Normal", properties.Template);    

    properties.Template = doc.AttachedTemplate;

    // "ContentStatus" هي خاصية وصفية مضمنة.
    properties.ContentStatus = "Draft";

    // عند الحفظ ، ستحتوي الخاصية المضمنة "ContentType" على نوع MIME لتنسيق حفظ الإخراج.
    Assert.AreEqual(string.Empty, properties.ContentType);

    // إذا كان المستند يحتوي على روابط ، وكانت جميعها محدثة ، فيمكننا تعيين خاصية "LinksUpToDate" على "true".
    Assert.False(properties.LinksUpToDate);

    doc.Save(ArtifactsDir + "DocumentProperties.Content.docx");
}

/// <summary>
/// تحسب الأسطر في مستند.
/// اجتياز شجرة كيانات تخطيط المستند عند الإنشاء ،
/// جرد الكيانات من نوع "السطر" التي تحتوي أيضًا على نص حقيقي.
/// </summary>
private class LineCounter
{
    public LineCounter(Document doc)
    {
        mLayoutEnumerator = new LayoutEnumerator(doc);

        CountLines();
    }

    public int GetLineCount()
    {
        return mLineCount;
    }

    private void CountLines()
    {
        do
        {
            if (mLayoutEnumerator.Type == LayoutEntityType.Line)
            {
                mScanningLineForRealText = true;
            }

            if (mLayoutEnumerator.MoveFirstChild())
            {
                if (mScanningLineForRealText && mLayoutEnumerator.Kind.StartsWith("TEXT"))
                {
                    mLineCount++;
                    mScanningLineForRealText = false;
                }
                CountLines();
                mLayoutEnumerator.MoveParent();
            }
        } while (mLayoutEnumerator.MoveNext());
    }

    private readonly LayoutEnumerator mLayoutEnumerator;
    private int mLineCount;
    private bool mScanningLineForRealText;
}
```

### أنظر أيضا

* class [BuiltInDocumentProperties](../)
* مساحة الاسم [Aspose.Words.Properties](../../builtindocumentproperties/)
* المجسم [Aspose.Words](../../../)


