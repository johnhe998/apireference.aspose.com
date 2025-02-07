---
title: Enum SaveFormat
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.SaveFormat تعداد. يشير إلى التنسيق الذي تم حفظ المستند به.
type: docs
weight: 4580
url: /ar/net/aspose.words/saveformat/
---
## SaveFormat enumeration

يشير إلى التنسيق الذي تم حفظ المستند به.

```csharp
public enum SaveFormat
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Unknown | `0` | قيمة افتراضية غير صالحة لتنسيق الملف. |
| Doc | `10` | يحفظ المستند بتنسيق Microsoft Word 97 - 2007 Document . |
| Dot | `11` | يحفظ المستند بتنسيق Microsoft Word 97 - 2007 Template . |
| Docx | `20` | يحفظ المستند كمستند معالجة Word XML مفتوح لـ Office (خالٍ من الماكرو) . |
| Docm | `21` | يحفظ المستند كمستند Office Open XML WordprocessingML Macro-Enabled . |
| Dotx | `22` | يحفظ المستند كقالب معالجة Word بتنسيق XML لـ Office Open XML (خالٍ من الماكرو) . |
| Dotm | `23` | يحفظ المستند كقالب معالجة Word XML مفتوح لـ Office. |
| FlatOpc | `24` | يحفظ المستند كملف Office Open XML WordprocessingML المخزن في ملف XML مسطح بدلاً من حزمة ZIP. |
| FlatOpcMacroEnabled | `25` | يحفظ المستند كمستند Office Open XML WordprocessingML Macro-Enabled المخزن في ملف XML ثابت بدلاً من حزمة ZIP. |
| FlatOpcTemplate | `26` | يحفظ المستند كـ Office Open XML WordprocessingML Template (خالٍ من الماكرو) المخزن في ملف XML ثابت بدلاً من حزمة ZIP. |
| FlatOpcTemplateMacroEnabled | `27` | يحفظ المستند كقالب Office Open XML WordprocessingML Macro-Enabled المخزن في ملف XML ثابت بدلاً من حزمة ZIP. |
| Rtf | `30` | يحفظ المستند بتنسيق RTF. يتم تخطي جميع الأحرف التي تزيد عن 7 بت كأحرف سداسية عشرية أو أحرف Unicode. |
| WordML | `31` | يحفظ المستند بتنسيق Microsoft Word 2003 WordprocessingML. |
| Pdf | `40` | يحفظ المستند بتنسيق PDF (Adobe Portable Document) . |
| Xps | `41` | يحفظ المستند بتنسيق XPS (مواصفات ورق XML) . |
| XamlFixed | `42` | يحفظ المستند بتنسيق Extensible Application Markup Language (XAML) كمستند ثابت. |
| Svg | `44` | يحفظ المستند بتنسيق Svg (Scalable Vector Graphics) . |
| HtmlFixed | `45` | يحفظ المستند بتنسيق HTML باستخدام العناصر ذات المواضع المطلقة |
| OpenXps | `46` | يحفظ المستند بتنسيق OpenXPS (Ecma-388) . |
| Ps | `47` | يحفظ المستند بتنسيق PS (PostScript). |
| Pcl | `48` | يحفظ المستند بتنسيق PCL (لغة التحكم في الطابعة). |
| Html | `50` | يحفظ المستند بتنسيق HTML . |
| Mhtml | `51` | يحفظ المستند بتنسيق MHTML (أرشيف الويب). |
| Epub | `52` | يحفظ المستند بتنسيق EPUB . |
| Odt | `60` | يحفظ المستند كمستند نصي ODF. |
| Ott | `61` | يحفظ المستند كقالب مستند نصي ODF. |
| Text | `70` | يحفظ المستند بتنسيق النص العادي. |
| XamlFlow | `71` | **بيتا.**يحفظ المستند بتنسيق Extensible Application Markup Language (XAML) كمستند تدفق. |
| XamlFlowPack | `72` | **بيتا.** يحفظ المستند بتنسيق حزمة لغة توصيف التطبيقات القابلة للتوسيع (XAML) كمستند تدفق. |
| Markdown | `73` | يحفظ المستند بتنسيق Markdown . |
| Tiff | `100` | يتم عرض صفحة أو صفحات من المستند وحفظها في ملف TIFF واحد أو متعدد الصفحات. |
| Png | `101` | يتم عرض صفحة من المستند وحفظها كملف PNG. |
| Bmp | `102` | يتم عرض صفحة من المستند وحفظها كملف BMP . |
| Emf | `103` | يعرض صفحة من المستند ويحفظها كملف متجه EMF (ملف تعريف محسّن). |
| Jpeg | `104` | يتم عرض صفحة من المستند وحفظها كملف JPEG . |
| Gif | `105` | يتم عرض صفحة من المستند وحفظها كملف GIF. |

### أمثلة

يوضح كيفية التحويل من تنسيق DOCX إلى تنسيق HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToHtml.html", SaveFormat.Html);
```

### أنظر أيضا

* method [Save](../document/save/)
* class [SaveOptions](../../aspose.words.saving/saveoptions/)
* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


