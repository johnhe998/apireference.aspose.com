---
title: Forms2OleControlCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: Forms2OleControlCollection ملكية. يحصلForms2OleControlالكائن في الفهرس المحدد.
type: docs
weight: 30
url: /ar/net/aspose.words.drawing.ole/forms2olecontrolcollection/item/
---
## Forms2OleControlCollection indexer

يحصل[`Forms2OleControl`](../../forms2olecontrol/)الكائن في الفهرس المحدد.

```csharp
public Forms2OleControl this[int index] { get; }
```

### أمثلة

يوضح كيفية الوصول إلى عنصر تحكم OLE مضمن في مستند وعناصر التحكم التابعة له.

```csharp
Document doc = new Document(MyDir + "OLE ActiveX controls.docm");

// تخزن الأشكال وتعرض كائنات OLE في نص المستند.
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.AreEqual("6e182020-f460-11ce-9bcd-00aa00608e01", shape.OleFormat.Clsid.ToString());

Forms2OleControl oleControl = (Forms2OleControl)shape.OleFormat.OleControl;

// قد تحتوي بعض عناصر تحكم OLE على عناصر تحكم تابعة ، مثل تلك الموجودة في هذا المستند مع ثلاثة أزرار خيارات.
Forms2OleControlCollection oleControlCollection = oleControl.ChildNodes;

Assert.AreEqual(3, oleControlCollection.Count);

Assert.AreEqual("C#", oleControlCollection[0].Caption);
Assert.AreEqual("1", oleControlCollection[0].Value);

Assert.AreEqual("Visual Basic", oleControlCollection[1].Caption);
Assert.AreEqual("0", oleControlCollection[1].Value);

Assert.AreEqual("Delphi", oleControlCollection[2].Caption);
Assert.AreEqual("0", oleControlCollection[2].Value);
```

### أنظر أيضا

* class [Forms2OleControl](../../forms2olecontrol/)
* class [Forms2OleControlCollection](../)
* مساحة الاسم [Aspose.Words.Drawing.Ole](../../forms2olecontrolcollection/)
* المجسم [Aspose.Words](../../../)


