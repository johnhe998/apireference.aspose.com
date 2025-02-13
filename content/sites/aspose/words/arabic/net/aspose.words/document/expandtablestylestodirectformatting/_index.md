---
title: Document.ExpandTableStylesToDirectFormatting
second_title: Aspose.Words لمراجع .NET API
description: Document طريقة. تحويل التنسيق المحدد في أنماط الجدول إلى تنسيق مباشر على الجداول في المستند.
type: docs
weight: 570
url: /ar/net/aspose.words/document/expandtablestylestodirectformatting/
---
## Document.ExpandTableStylesToDirectFormatting method

تحويل التنسيق المحدد في أنماط الجدول إلى تنسيق مباشر على الجداول في المستند.

```csharp
public void ExpandTableStylesToDirectFormatting()
```

### ملاحظات

توجد هذه الطريقة لأن هذا الإصدار من Aspose.Words يوفر دعمًا محدودًا لأنماط الجدول (انظر أدناه). قد تكون هذه الطريقة مفيدة عند تحميل مستند DOCX أو WordprocessingML يحتوي على جداول منسقة بأنماط جدول وتحتاج إلى الاستعلام عن تنسيق جداول أو خلايا أو فقرات أو نص.

يوفر هذا الإصدار من Aspose.Words دعمًا محدودًا لأنماط الجدول على النحو التالي:

* يتم الاحتفاظ بأنماط الجدول المحددة في مستندات DOCX أو WordprocessingML كأنماط جدول عند حفظ المستند بتنسيق DOCX أو WordprocessingML.
* يتم تحويل أنماط الجدول المحددة في مستندات DOCX أو WordprocessingML تلقائيًا إلى تنسيق مباشر على الجداول عند حفظ المستند في أي تنسيق آخر ، عرض أو طباعة .
* يتم الاحتفاظ بأنماط الجدول المحددة في مستندات DOC كأنماط جدول عندما_ حفظ المستند كـ DOC فقط.

### أمثلة

يوضح كيفية تطبيق خصائص نمط الجدول مباشرة على عناصر الجدول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// تتعلق هذه الطريقة بخصائص نمط الجدول مثل تلك التي حددناها أعلاه.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


