---
title: Forms2OleControl.Value
second_title: Aspose.Words for .NET API Referansı
description: Forms2OleControl mülk. Genellikle kontrol durumunu temsil eden temel Değer özelliğini alır. Örneğin işaretli seçenek düğmesi 1 değerine sahipken işaretlenmemişse 0 değerine sahiptir. Varsayılan değer boş bir dizedir.
type: docs
weight: 60
url: /tr/net/aspose.words.drawing.ole/forms2olecontrol/value/
---
## Forms2OleControl.Value property

Genellikle kontrol durumunu temsil eden temel Değer özelliğini alır. Örneğin, işaretli seçenek düğmesi '1' değerine sahipken, işaretlenmemişse '0' değerine sahiptir. Varsayılan değer boş bir dizedir.

```csharp
public string Value { get; }
```

### Örnekler

ActiveX denetiminin özelliklerinin nasıl doğrulanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");

Shape shape = (Shape) doc.GetChild(NodeType.Shape, 0, true);
OleControl oleControl = shape.OleFormat.OleControl;

Assert.AreEqual(null, oleControl.Name);

if (oleControl.IsForms2OleControl)
{
    Forms2OleControl checkBox = (Forms2OleControl) oleControl;
    Assert.AreEqual("Первый", checkBox.Caption);
    Assert.AreEqual("0", checkBox.Value);
    Assert.AreEqual(true, checkBox.Enabled);
    Assert.AreEqual(Forms2OleControlType.CheckBox, checkBox.Type);
    Assert.AreEqual(null, checkBox.ChildNodes);
}
```

### Ayrıca bakınız

* class [Forms2OleControl](../)
* ad alanı [Aspose.Words.Drawing.Ole](../../forms2olecontrol/)
* toplantı [Aspose.Words](../../../)


