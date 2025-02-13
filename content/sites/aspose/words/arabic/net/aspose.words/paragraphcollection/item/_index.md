---
title: ParagraphCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: ParagraphCollection ملكية. يسترجع أ فقرة في الفهرس المحدد.
type: docs
weight: 10
url: /ar/net/aspose.words/paragraphcollection/item/
---
## ParagraphCollection indexer

يسترجع أ **فقرة** في الفهرس المحدد.

```csharp
public Paragraph this[int index] { get; }
```

| معامل | وصف |
| --- | --- |
| index | فهرس في المجموعة. |

### ملاحظات

المؤشر على أساس الصفر.

يُسمح بالفهارس السلبية وتشير إلى الوصول من الجزء الخلفي من المجموعة. على سبيل المثال -1 تعني العنصر الأخير ، -2 تعني العنصر الثاني قبل الأخير وهكذا.

إذا كان الفهرس أكبر من أو يساوي عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

إذا كان الفهرس سالبًا وكانت قيمته المطلقة أكبر من عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

### أمثلة

يوضح كيفية التحقق مما إذا كانت الفقرة عبارة عن مراجعة للحركة.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// يحتوي هذا المستند على مراجعات "نقل" ، والتي تظهر عندما نبرز النص بالمؤشر ،
// ثم اسحبه لنقله إلى موقع آخر
// أثناء تتبع المراجعات في Microsoft Word عبر "مراجعة" - >; "تعقب التغيرات".
Assert.AreEqual(6, doc.Revisions.Count(r => r.RevisionType == RevisionType.Moving));

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

// نقل المراجعات تتكون من أزواج من المراجعات "الانتقال من" و "الانتقال إلى". 
// هذه المراجعات هي تغييرات محتملة على المستند يمكننا إما قبولها أو رفضها.
// قبل أن نقبل / نرفض مراجعة النقل ، المستند
// يجب أن يتتبع كلاً من وجهات المغادرة والوصول للنص.
// تحدد الفقرتان الثانية والرابعة أحد هذه المراجعة ، وبالتالي فإن كلاهما لهما نفس المحتويات.
Assert.AreEqual(paragraphs[1].GetText(), paragraphs[3].GetText());

// مراجعة "الانتقال من" هي الفقرة التي سحبنا النص منها.
// إذا قبلنا المراجعة ، ستختفي هذه الفقرة ،
// والآخر سيبقى ولن يكون مراجعة.
Assert.True(paragraphs[1].IsMoveFromRevision);

// مراجعة "الانتقال إلى" هي الفقرة التي سحبنا النص إليها.
// إذا رفضنا المراجعة ، فستختفي هذه الفقرة بدلاً من ذلك ، وستبقى الأخرى.
Assert.True(paragraphs[3].IsMoveToRevision);
```

### أنظر أيضا

* class [Paragraph](../../paragraph/)
* class [ParagraphCollection](../)
* مساحة الاسم [Aspose.Words](../../paragraphcollection/)
* المجسم [Aspose.Words](../../../)


