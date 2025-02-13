---
title: Enum MailMergeDataType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Settings.MailMergeDataType تعداد. تحديد نوع مصدر بيانات دمج البريد الخارجي.
type: docs
weight: 5520
url: /ar/net/aspose.words.settings/mailmergedatatype/
---
## MailMergeDataType enumeration

تحديد نوع مصدر بيانات دمج البريد الخارجي.

```csharp
public enum MailMergeDataType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `-1` | لم يتم تحديد مصدر بيانات لدمج المراسلات. |
| TextFile | `0` | تحديد أن مستندًا معينًا قد تم توصيله بملف نصي عبر نظام تبادل البيانات الديناميكي (DDE). |
| Database | `1` | تحديد أن مستندًا معينًا قد تم توصيله بقاعدة بيانات Access عبر نظام تبادل البيانات الديناميكي (DDE). |
| Spreadsheet | `2` | يحدد أن مستندًا معينًا قد تم توصيله بجدول بيانات Excel عبر نظام تبادل البيانات الديناميكي (DDE). |
| Query | `3` | تحديد أن مستندًا معينًا قد تم توصيله بمصدر بيانات خارجي باستخدام أداة استعلام خارجية. |
| Odbc | `4` | يحدد أن مستندًا معينًا قد تم توصيله بمصدر بيانات خارجي عبر واجهة اتصال قاعدة البيانات المفتوحة. |
| Native | `5` | يحدد أن مستندًا معينًا قد تم توصيله بمصدر بيانات خارجي عبر واجهة Office Data Source Object (ODSO). |
| Default | `-1` | يساويNone . |

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

* property [DataType](../mailmergesettings/datatype/)
* مساحة الاسم [Aspose.Words.Settings](../../aspose.words.settings/)
* المجسم [Aspose.Words](../../)


