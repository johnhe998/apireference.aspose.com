---
title: XmlMapping.Delete
second_title: Aspose.Words لمراجع .NET API
description: XmlMapping طريقة. حذف تعيين المستند الأصلي المهيكل إلى بيانات XML.
type: docs
weight: 60
url: /ar/net/aspose.words.markup/xmlmapping/delete/
---
## XmlMapping.Delete method

حذف تعيين المستند الأصلي المهيكل إلى بيانات XML.

```csharp
public void Delete()
```

### أمثلة

يوضح كيفية تعيين تعيينات XML لأجزاء XML المخصصة.

```csharp
Document doc = new Document();

// إنشاء جزء XML يحتوي على نص وإضافته إلى مجموعة CustomXmlPart الخاصة بالمستند.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual("<root><text>Text element #1</text><text>Text element #2</text></root>", 
    Encoding.UTF8.GetString(xmlPart.Data));

// قم بإنشاء علامة مستند منظم تعرض محتويات CustomXmlPart الخاصة بنا.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);

// تعيين تعيين لعلامة المستند المنظمة الخاصة بنا. هذا التعيين سوف يوجه
// علامة المستند المهيكلة الخاصة بنا لعرض جزء من محتويات نص جزء XML الذي يشير إليه XPath.
// في هذه الحالة ، ستكون محتويات الثانية "< text >" عنصر أول "< root >" العنصر: "عنصر النص رقم 2".
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", "xmlns:ns='http://www.w3.org/2001/XMLSchema ") ;

Assert.True(tag.XmlMapping.IsMapped);
Assert.AreEqual(xmlPart, tag.XmlMapping.CustomXmlPart);
Assert.AreEqual("/root[1]/text[2]", tag.XmlMapping.XPath);
Assert.AreEqual("xmlns:ns='http://www.w3.org/2001/XMLSchema '"، tag.XmlMapping.PrefixMappings) ;

// أضف علامة المستند المهيكلة إلى المستند لعرض المحتوى من الجزء المخصص لدينا.
doc.FirstSection.Body.AppendChild(tag);
doc.Save(ArtifactsDir + "StructuredDocumentTag.XmlMapping.docx");
```

### أنظر أيضا

* class [XmlMapping](../)
* مساحة الاسم [Aspose.Words.Markup](../../xmlmapping/)
* المجسم [Aspose.Words](../../../)


