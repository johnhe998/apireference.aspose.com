---
title: Odso.ColumnDelimiter
second_title: Aspose.Words لمراجع .NET API
description: Odso ملكية. يحدد الحرف الذي يجب تفسيره على أنه محدد العمود المستخدم لفصل الأعمدة داخل مصادر البيانات الخارجية. القيمة الافتراضية هي 0 مما يعني عدم وجود محدد عمود محدد.
type: docs
weight: 20
url: /ar/net/aspose.words.settings/odso/columndelimiter/
---
## Odso.ColumnDelimiter property

يحدد الحرف الذي يجب تفسيره على أنه محدد العمود المستخدم لفصل الأعمدة داخل مصادر البيانات الخارجية. القيمة الافتراضية هي 0 مما يعني عدم وجود محدد عمود محدد.

```csharp
public char ColumnDelimiter { get; set; }
```

### ملاحظات

RK لم أر هذا قيد الاستخدام من قبل.

### أمثلة

يوضح كيفية تنفيذ دمج البريد مع البيانات من كائن مصدر بيانات Office.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// إنشاء مصدر بيانات في شكل ملف ASCII ، باستخدام "|" حرف
// يعمل كمحدد يفصل بين الأعمدة. يحتوي السطر الأول على أسماء الأعمدة الثلاثة ،
// وكل سطر لاحق هو صف بقيمها الخاصة.
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// سيؤدي فتح هذا المستند في Microsoft Word إلى تنفيذ دمج البريد قبل عرض المحتويات. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### أنظر أيضا

* class [Odso](../)
* مساحة الاسم [Aspose.Words.Settings](../../odso/)
* المجسم [Aspose.Words](../../../)


