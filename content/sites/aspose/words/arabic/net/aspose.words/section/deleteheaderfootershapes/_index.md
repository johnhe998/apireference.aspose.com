---
title: Section.DeleteHeaderFooterShapes
second_title: Aspose.Words لمراجع .NET API
description: Section طريقة. حذف كافة الأشكال الكائنات الرسومية من رؤوس وتذييلات هذا القسم .
type: docs
weight: 120
url: /ar/net/aspose.words/section/deleteheaderfootershapes/
---
## Section.DeleteHeaderFooterShapes method

حذف كافة الأشكال (الكائنات الرسومية) من رؤوس وتذييلات هذا القسم .

```csharp
public void DeleteHeaderFooterShapes()
```

### أمثلة

يوضح كيفية إزالة كافة الأشكال من كافة تذييلات الرؤوس في مقطع ما.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إنشاء رأس أساسي بشكل.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.InsertShape(ShapeType.Rectangle, 100, 100);

// إنشاء تذييل أساسي بصورة.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.InsertImage(ImageDir + "Logo Icon.ico");

Assert.AreEqual(1, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetChildNodes(NodeType.Shape, true).Count);
Assert.AreEqual(1, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetChildNodes(NodeType.Shape, true).Count);

// قم بإزالة كافة الأشكال من الرؤوس والتذييلات في القسم الأول.
doc.FirstSection.DeleteHeaderFooterShapes();

Assert.AreEqual(0, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetChildNodes(NodeType.Shape, true).Count);
Assert.AreEqual(0, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetChildNodes(NodeType.Shape, true).Count);
```

### أنظر أيضا

* class [Section](../)
* مساحة الاسم [Aspose.Words](../../section/)
* المجسم [Aspose.Words](../../../)


