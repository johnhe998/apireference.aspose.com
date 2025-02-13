---
title: Enum FontFamily
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FontFamily تعداد. يمثل عائلة الخطوط .
type: docs
weight: 2730
url: /ar/net/aspose.words.fonts/fontfamily/
---
## FontFamily enumeration

يمثل عائلة الخطوط .

```csharp
public enum FontFamily
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Auto | `0` | تحديد اسم عائلة عام. يتم استخدام هذا الاسم عندما لا توجد معلومات حول خط أو لا يهم. يتم استخدام الخط الافتراضي. |
| Roman | `1` | تحديد خط متناسب مع serifs. مثال على ذلك Times New Roman . |
| Swiss | `2` | يحدد خطًا متناسبًا بدون serifs. مثال على ذلك Arial . |
| Modern | `3` | يحدد خط monospace مع أو بدون serifs. عادةً ما تكون خطوط Monospace حديثة ؛ تشمل الأمثلة Pica و Elite و Courier New. |
| Script | `4` | تحديد خط مصمم ليبدو مثل الكتابة اليدوية ؛ تتضمن الأمثلة Script و Cursive. |
| Decorative | `5` | تحديد خط جديد. مثال على ذلك هو اللغة الإنجليزية القديمة. |

### ملاحظات

مجموعة الخطوط هي مجموعة من الخطوط التي لها خصائص عرض وخصائص serif مشتركة.

### أمثلة

يوضح كيفية الوصول إلى تفاصيل كل خط في المستند وطباعتها.

```csharp
Document doc = new Document(MyDir + "Document.docx");

IEnumerator<FontInfo> fontCollectionEnumerator = doc.FontInfos.GetEnumerator();
while (fontCollectionEnumerator.MoveNext())
{
    FontInfo fontInfo = fontCollectionEnumerator.Current;
    if (fontInfo != null)
    {
        Console.WriteLine("Font name: " + fontInfo.Name);

        // عادةً ما تكون أسماء Alt فارغة.
        Console.WriteLine("Alt name: " + fontInfo.AltName);
        Console.WriteLine("\t- Family: " + fontInfo.Family);
        Console.WriteLine("\t- " + (fontInfo.IsTrueType ? "Is TrueType" : "Is not TrueType"));
        Console.WriteLine("\t- Pitch: " + fontInfo.Pitch);
        Console.WriteLine("\t- Charset: " + fontInfo.Charset);
        Console.WriteLine("\t- Panose:");
        Console.WriteLine("\t\tFamily Kind: " + fontInfo.Panose[0]);
        Console.WriteLine("\t\tSerif Style: " + fontInfo.Panose[1]);
        Console.WriteLine("\t\tWeight: " + fontInfo.Panose[2]);
        Console.WriteLine("\t\tProportion: " + fontInfo.Panose[3]);
        Console.WriteLine("\t\tContrast: " + fontInfo.Panose[4]);
        Console.WriteLine("\t\tStroke Variation: " + fontInfo.Panose[5]);
        Console.WriteLine("\t\tArm Style: " + fontInfo.Panose[6]);
        Console.WriteLine("\t\tLetterform: " + fontInfo.Panose[7]);
        Console.WriteLine("\t\tMidline: " + fontInfo.Panose[8]);
        Console.WriteLine("\t\tX-Height: " + fontInfo.Panose[9]);
    }
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


