---
title: TableStyle.RowStripe
second_title: Aspose.Words لمراجع .NET API
description: TableStyle ملكية. الحصول على أو تعيين عدد من الصفوف لتضمينها في النطاق عندما يحدد النمط نطاق الصفوف الفردية / الزوجية.
type: docs
weight: 120
url: /ar/net/aspose.words/tablestyle/rowstripe/
---
## TableStyle.RowStripe property

الحصول على أو تعيين عدد من الصفوف لتضمينها في النطاق عندما يحدد النمط نطاق الصفوف الفردية / الزوجية.

```csharp
public int RowStripe { get; set; }
```

### أمثلة

يوضح كيفية إنشاء أنماط جدول شرطية تتناوب بين الصفوف.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يمكننا تكوين نمط شرطي للجدول لتطبيق لون مختلف على الصف / العمود ،
// استنادًا إلى ما إذا كان الصف / العمود زوجيًا أم فرديًا ، مما يؤدي إلى إنشاء نمط لوني بديل.
// يمكننا أيضًا تطبيق رقم n على نطاقات الصف / العمود ،
// مما يعني أن اللون يتغير بعد كل n من الصفوف / الأعمدة بدلاً من واحد.
// قم بإنشاء جدول حيث سيتم ربط الأعمدة والصفوف الفردية في مجموعات من ثلاثة.
Table table = builder.StartTable();
for (int i = 0; i < 15; i++)
{
    for (int j = 0; j < 4; j++)
    {
        builder.InsertCell();
        builder.Writeln($"{(j % 2 == 0 ? "Even" : "Odd")} column.");
        builder.Write($"Row banding {(i % 3 == 0 ? "start" : "continuation")}.");
    }
    builder.EndRow();
}
builder.EndTable();

// تطبيق نمط خط على كل حدود الجدول.
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.Color = Color.Black;
tableStyle.Borders.LineStyle = LineStyle.Double;

// اضبط اللونين اللذين سيتناوبان على كل 3 صفوف.
tableStyle.RowStripe = 3;
tableStyle.ConditionalStyles[ConditionalStyleType.OddRowBanding].Shading.BackgroundPatternColor = Color.LightBlue;
tableStyle.ConditionalStyles[ConditionalStyleType.EvenRowBanding].Shading.BackgroundPatternColor = Color.LightCyan;

// عيِّن لونًا لتطبيقه على كل عمود زوجي ، والذي سيتجاوز أي تلوين صف مخصص.
tableStyle.ColumnStripe = 1;
tableStyle.ConditionalStyles[ConditionalStyleType.EvenColumnBanding].Shading.BackgroundPatternColor = Color.LightSalmon;

table.Style = tableStyle;

// تتيح خاصية "StyleOptions" ربط الصفوف افتراضيًا.
Assert.AreEqual(TableStyleOptions.FirstRow | TableStyleOptions.FirstColumn | TableStyleOptions.RowBands,
    table.StyleOptions);

// استخدم خاصية "StyleOptions" أيضًا لتمكين ربط الأعمدة.
table.StyleOptions = table.StyleOptions | TableStyleOptions.ColumnBands;

doc.Save(ArtifactsDir + "Table.AlternatingRowStyles.docx");
```

### أنظر أيضا

* class [TableStyle](../)
* مساحة الاسم [Aspose.Words](../../tablestyle/)
* المجسم [Aspose.Words](../../../)


