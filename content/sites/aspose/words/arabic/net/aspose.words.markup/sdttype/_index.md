---
title: Enum SdtType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Markup.SdtType تعداد. يحدد نوع عقدة علامة المستند المهيكلة SDT.
type: docs
weight: 3800
url: /ar/net/aspose.words.markup/sdttype/
---
## SdtType enumeration

يحدد نوع عقدة علامة المستند المهيكلة (SDT).

```csharp
public enum SdtType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | لم يتم تعيين نوع إلى SDT . |
| Bibliography | `1` | تمثل المعاملة الخاصة والتفضيلية إدخالاً ببليوغرافيا. |
| Citation | `2` | تمثل المعاملة الخاصة والتفضيلية استشهادًا . |
| Equation | `3` | تمثل المعاملة الخاصة والتفضيلية معادلة . |
| DropDownList | `4` | تمثل SDT قائمة منسدلة عند عرضها في المستند. |
| ComboBox | `5` | تمثل SDT مربع تحرير وسرد عند عرضها في المستند. |
| Date | `6` | تمثل SDT منتقي التاريخ عند عرضها في المستند. |
| BuildingBlockGallery | `7` | تمثل SDT نوع معرض كتل الإنشاء. |
| DocPartObj | `8` | تمثل SDT نوع جزء المستند. |
| Group | `9` | تمثل SDT مجموعة مقيدة عند عرضها في المستند. |
| Picture | `10` | تمثل SDT صورة عند عرضها في المستند. |
| RichText | `11` | تمثل SDT مربع نص منسق عند عرضها في المستند. |
| PlainText | `12` | تمثل SDT مربع نص عادي عند عرضها في المستند. |
| Checkbox | `13` | تمثل SDT خانة اختيار عند عرضها في المستند. |
| RepeatingSection | `14` | تمثل SDT نوع قسم متكرر عند عرضها في المستند. |
| RepeatingSectionItem | `15` | تمثل SDT عنصر قسم متكرر. |
| EntityPicker | `16` | تمثل SDT منتقي الكيانات الذي يسمح للمستخدم بتحديد مثيل لنوع محتوى خارجي. |

### أمثلة

يوضح كيفية العمل باستخدام أنماط عناصر التحكم في المحتوى.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي طريقتان لتطبيق نمط من المستند إلى علامة مستند منظم.
// 1 - تطبيق كائن نمط من مجموعة أنماط المستند:
Style quoteStyle = doc.Styles[StyleIdentifier.Quote];
StructuredDocumentTag sdtPlainText =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline) { Style = quoteStyle };

// 2 - الإشارة إلى نمط في المستند بالاسم:
StructuredDocumentTag sdtRichText =
    new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Inline) { StyleName = "Quote" };

builder.InsertNode(sdtPlainText);
builder.InsertNode(sdtRichText);

Assert.AreEqual(NodeType.StructuredDocumentTag, sdtPlainText.NodeType);

NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true);

foreach (Node node in tags)
{
    StructuredDocumentTag sdt = (StructuredDocumentTag)node;

    Assert.AreEqual(StyleIdentifier.Quote, sdt.Style.StyleIdentifier);
    Assert.AreEqual("Quote", sdt.StyleName);
}
```

يوضح كيفية تعبئة جدول ببيانات من جزء XML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books>" +
        "<book>" +
            "<title>Everyday Italian</title>" +
            "<author>Giada De Laurentiis</author>" +
        "</book>" +
        "<book>" +
            "<title>The C Programming Language</title>" +
            "<author>Brian W. Kernighan, Dennis M. Ritchie</author>" +
        "</book>" +
        "<book>" +
            "<title>Learning XML</title>" +
            "<author>Erik T. Ray</author>" +
        "</book>" +
    "</books>");

// إنشاء رؤوس للبيانات من محتوى XML.
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();

// قم بإنشاء جدول به قسم مكرر بالداخل.
StructuredDocumentTag repeatingSectionSdt =
    new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", string.Empty);
table.AppendChild(repeatingSectionSdt);

// أضف عنصر قسم متكرر داخل قسم التكرار وقم بتمييزه كصف.
// سيحتوي هذا الجدول على صف لكل عنصر يمكننا العثور عليه في مستند XML
// باستخدام "/ books [1] / book" XPath ، منها ثلاثة.
StructuredDocumentTag repeatingSectionItemSdt =
    new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);

// تعيين بيانات XML بخلايا جدول تم إنشاؤها لعنوان كل كتاب ومؤلفه.
StructuredDocumentTag titleSdt =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", string.Empty);
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", string.Empty);
row.AppendChild(authorSdt);

doc.Save(ArtifactsDir + "StructuredDocumentTag.RepeatingSectionItem.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Markup](../../aspose.words.markup/)
* المجسم [Aspose.Words](../../)


