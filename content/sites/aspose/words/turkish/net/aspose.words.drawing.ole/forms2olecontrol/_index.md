---
title: Class Forms2OleControl
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Ole.Forms2OleControl sınıf. Microsoft Forms 2.0 OLE denetimini temsil eder.
type: docs
weight: 980
url: /tr/net/aspose.words.drawing.ole/forms2olecontrol/
---
## Forms2OleControl class

Microsoft Forms 2.0 OLE denetimini temsil eder.

```csharp
public abstract class Forms2OleControl : OleControl
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Caption](../../aspose.words.drawing.ole/forms2olecontrol/caption/) { get; } | Denetimin Altyazı özelliğini alır. Varsayılan değer boş bir dizedir. |
| [ChildNodes](../../aspose.words.drawing.ole/forms2olecontrol/childnodes/) { get; } | Anında alt denetimlerin koleksiyonunu alır. |
| [Enabled](../../aspose.words.drawing.ole/forms2olecontrol/enabled/) { get; } | Denetim etkin durumdaysa true değerini döndürür. |
| override [IsForms2OleControl](../../aspose.words.drawing.ole/forms2olecontrol/isforms2olecontrol/) { get; } |  |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | ActiveX denetiminin adını alır. |
| [Type](../../aspose.words.drawing.ole/forms2olecontrol/type/) { get; } | Forms 2.0 denetimi türünü alır. |
| [Value](../../aspose.words.drawing.ole/forms2olecontrol/value/) { get; } | Genellikle kontrol durumunu temsil eden temel Değer özelliğini alır. Örneğin, işaretli seçenek düğmesi '1' değerine sahipken, işaretlenmemişse '0' değerine sahiptir. Varsayılan değer boş bir dizedir. |

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

* class [OleControl](../olecontrol/)
* ad alanı [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* toplantı [Aspose.Words](../../)


