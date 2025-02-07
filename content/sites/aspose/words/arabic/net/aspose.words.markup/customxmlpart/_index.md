---
title: Class CustomXmlPart
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Markup.CustomXmlPart فصل. يمثل جزء تخزين بيانات XML مخصص بيانات XML مخصصة داخل حزمة .
type: docs
weight: 3680
url: /ar/net/aspose.words.markup/customxmlpart/
---
## CustomXmlPart class

يمثل جزء تخزين بيانات XML مخصص (بيانات XML مخصصة داخل حزمة) .

```csharp
public class CustomXmlPart
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [CustomXmlPart](customxmlpart/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Data](../../aspose.words.markup/customxmlpart/data/) { get; set; } | الحصول على محتوى XML لجزء تخزين بيانات XML المخصص هذا أو تعيينه. |
| [DataChecksum](../../aspose.words.markup/customxmlpart/datachecksum/) { get; } | يحدد المجموع الاختباري لفحص التكرار الدوري (CRC) لملف[`Data`](./data/) المحتوى . |
| [Id](../../aspose.words.markup/customxmlpart/id/) { get; set; } | الحصول على أو تعيين السلسلة التي تحدد جزء XML المخصص هذا داخل مستند OOXML. |
| [Schemas](../../aspose.words.markup/customxmlpart/schemas/) { get; } | تحديد مجموعة مخططات XML المرتبطة بجزء XML المخصص هذا. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Clone](../../aspose.words.markup/customxmlpart/clone/)() | عمل نسخة "عميقة بدرجة كافية" من الكائن. لا يكرر بايتات ملف[`Data`](./data/) القيمة . |

### ملاحظات

يمكن أن يحتوي مستند DOCX أو DOC على واحد أو أكثر من أجزاء تخزين بيانات XML المخصصة. يحتفظ Aspose.Words و بإنشاء واستخراج بيانات XML المخصصة عبر ملف[`CustomXmlParts`](../../aspose.words/document/customxmlparts/) مجموعة.

### أمثلة

يوضح كيفية إنشاء علامة مستند منظم ببيانات XML مخصصة.

```csharp
Document doc = new Document();

// إنشاء جزء XML يحتوي على بيانات وإضافته إلى مجموعة المستند.
// إذا قمنا بتمكين علامة التبويب "المطور" في Microsoft Word ،
// يمكننا العثور على عناصر من هذه المجموعة في "جزء تعيين XML" ، جنبًا إلى جنب مع بعض العناصر الافتراضية.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello world!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual(Encoding.ASCII.GetBytes(xmlPartContent), xmlPart.Data);
Assert.AreEqual(xmlPartId, xmlPart.Id);

// فيما يلي طريقتان للإشارة إلى أجزاء XML.
// 1 - بواسطة فهرس في مجموعة أجزاء XML المخصصة:
Assert.AreEqual(xmlPart, doc.CustomXmlParts[0]);

// 2 - بواسطة GUID:
Assert.AreEqual(xmlPart, doc.CustomXmlParts.GetById(xmlPartId));

// إضافة اقتران مخطط XML.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema ") ;

// استنساخ جزء ، ثم أدخله في المجموعة.
CustomXmlPart xmlPartClone = xmlPart.Clone();
xmlPartClone.Id = Guid.NewGuid().ToString("B");
doc.CustomXmlParts.Add(xmlPartClone);

Assert.AreEqual(2, doc.CustomXmlParts.Count);

// تكرار خلال المجموعة وطباعة محتويات كل جزء.
using (IEnumerator<CustomXmlPart> enumerator = doc.CustomXmlParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"XML part index {index}, ID: {enumerator.Current.Id}");
        Console.WriteLine($"\tContent: {Encoding.UTF8.GetString(enumerator.Current.Data)}");
        index++;
    }
}

// استخدم طريقة "RemoveAt" لإزالة الجزء المستنسخ بالفهرس.
doc.CustomXmlParts.RemoveAt(1);

Assert.AreEqual(1, doc.CustomXmlParts.Count);

// استنساخ مجموعة أجزاء XML ، ثم استخدم طريقة "Clear" لإزالة جميع عناصرها مرة واحدة.
CustomXmlPartCollection customXmlParts = doc.CustomXmlParts.Clone();
customXmlParts.Clear();

// قم بإنشاء علامة مستند منظم تعرض محتويات الجزء الخاص بنا وإدراجها في نص المستند.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", string.Empty);

doc.FirstSection.Body.AppendChild(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CustomXml.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Markup](../../aspose.words.markup/)
* المجسم [Aspose.Words](../../)


