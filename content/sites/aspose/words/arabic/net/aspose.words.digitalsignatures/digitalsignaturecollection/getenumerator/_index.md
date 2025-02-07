---
title: DigitalSignatureCollection.GetEnumerator
second_title: Aspose.Words لمراجع .NET API
description: DigitalSignatureCollection طريقة. إرجاع كائن تعداد القاموس الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة.
type: docs
weight: 50
url: /ar/net/aspose.words.digitalsignatures/digitalsignaturecollection/getenumerator/
---
## DigitalSignatureCollection.GetEnumerator method

إرجاع كائن تعداد القاموس الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة.

```csharp
public IEnumerator<DigitalSignature> GetEnumerator()
```

### أمثلة

يوضح كيفية طباعة جميع التوقيعات الرقمية لوثيقة موقعة.

```csharp
DigitalSignatureCollection digitalSignatures =
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

using (IEnumerator<DigitalSignature> enumerator = digitalSignatures.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        DigitalSignature ds = enumerator.Current;

        if (ds != null)
            Console.WriteLine(ds.ToString());
    }
}
```

### أنظر أيضا

* class [DigitalSignature](../../digitalsignature/)
* class [DigitalSignatureCollection](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignaturecollection/)
* المجسم [Aspose.Words](../../../)


