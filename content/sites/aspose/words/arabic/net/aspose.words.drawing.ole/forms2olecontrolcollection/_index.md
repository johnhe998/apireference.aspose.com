---
title: Class Forms2OleControlCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Ole.Forms2OleControlCollection فصل. يمثل مجموعة منForms2OleControl الكائنات .
type: docs
weight: 990
url: /ar/net/aspose.words.drawing.ole/forms2olecontrolcollection/
---
## Forms2OleControlCollection class

يمثل مجموعة من[`Forms2OleControl`](../forms2olecontrol/) الكائنات .

```csharp
public class Forms2OleControlCollection
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [Forms2OleControlCollection](forms2olecontrolcollection/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.drawing.ole/forms2olecontrolcollection/count/) { get; } | الحصول على عدد العناصر في المجموعة . |
| [Item](../../aspose.words.drawing.ole/forms2olecontrolcollection/item/) { get; } | يحصل[`Forms2OleControl`](../forms2olecontrol/)الكائن في الفهرس المحدد. |

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

* مساحة الاسم [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* المجسم [Aspose.Words](../../)


