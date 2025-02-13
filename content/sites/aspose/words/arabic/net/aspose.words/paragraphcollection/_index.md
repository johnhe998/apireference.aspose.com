---
title: Class ParagraphCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ParagraphCollection فصل. يوفر وصولاً مكتوبًا إلى مجموعة منParagraph العقد .
type: docs
weight: 4170
url: /ar/net/aspose.words/paragraphcollection/
---
## ParagraphCollection class

يوفر وصولاً مكتوبًا إلى مجموعة من[`Paragraph`](../paragraph/) العقد .

```csharp
public class ParagraphCollection : NodeCollection
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | الحصول على عدد العقد في المجموعة. |
| [Item](../../aspose.words/paragraphcollection/item/) { get; } | يسترجع أ **فقرة** في الفهرس المحدد. (2 indexers) |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | يضيف عقدة إلى نهاية المجموعة. |
| [Clear](../../aspose.words/nodecollection/clear/)() | يزيل كافة العقد من هذه المجموعة ومن المستند. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | لتحديد ما إذا كانت العقدة موجودة في المجموعة. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | يوفر تكرارًا بسيطًا لنمط "foreach" عبر مجموعة العقد. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | إرجاع الفهرس الصفري للعقدة المحددة. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | إدراج عقدة في المجموعة بالفهرس المحدد. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | يزيل العقدة من المجموعة ومن الوثيقة. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | يزيل العقدة في الفهرس المحدد من المجموعة ومن المستند. |
| [ToArray](../../aspose.words/paragraphcollection/toarray/#toarray_1)() | ينسخ كل الفقرات من المجموعة إلى مصفوفة جديدة من الفقرات. (2 methods) |

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

* class [NodeCollection](../nodecollection/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


