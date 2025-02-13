---
title: FieldNextIf.RightExpression
second_title: Справочник по API Aspose.Words для .NET
description: FieldNextIf свойство. Получает или задает правую часть выражения сравнения.
type: docs
weight: 40
url: /ru/net/aspose.words.fields/fieldnextif/rightexpression/
---
## FieldNextIf.RightExpression property

Получает или задает правую часть выражения сравнения.

```csharp
public string RightExpression { get; set; }
```

### Примеры

Показывает, как использовать поля NEXT/NEXTIF для объединения нескольких строк в одну страницу во время слияния почты.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Создадим источник данных для нашего слияния с 3 строками.
    // Слияние почты, использующее эту таблицу, обычно создает 3-страничный документ.
    DataTable table = new DataTable("Employees");
    table.Columns.Add("Courtesy Title");
    table.Columns.Add("First Name");
    table.Columns.Add("Last Name");
    table.Rows.Add("Mr.", "John", "Doe");
    table.Rows.Add("Mrs.", "Jane", "Cardholder");
    table.Rows.Add("Mr.", "Joe", "Bloggs");

    InsertMergeFields(builder, "First row: ");

    // Если у нас есть несколько полей слияния с одним и тем же FieldName,
    // они будут получать данные из той же строки источника данных и отображать одно и то же значение после слияния.
    // Поле NEXT указывает почтовому слиянию немедленно перейти на одну строку вниз,
    // что означает, что любые поля MERGEFIELD, которые следуют за полем NEXT, будут получать данные из следующей строки.
    // Убедитесь, что вы никогда не пытаетесь перейти к следующей строке, когда уже находитесь в последней строке.
    FieldNext fieldNext = (FieldNext)builder.InsertField(FieldType.FieldNext, true);

    Assert.AreEqual(" NEXT ", fieldNext.GetFieldCode());

    // После слияния значения источника данных, которые принимают эти поля MERGEFIELD
     // окажется на той же странице, что и поля MERGEFIELD выше.
    InsertMergeFields(builder, "Second row: ");

    // Поле NEXTIF имеет ту же функцию, что и поле NEXT,
    // но он переходит к следующей строке только в том случае, если утверждение, созданное следующими тремя свойствами, истинно.
    FieldNextIf fieldNextIf = (FieldNextIf)builder.InsertField(FieldType.FieldNextIf, true);
    fieldNextIf.LeftExpression = "5";
    fieldNextIf.RightExpression = "2 + 3";
    fieldNextIf.ComparisonOperator = "=";

    Assert.AreEqual(" NEXTIF  5 = \"2 + 3\"", fieldNextIf.GetFieldCode());

    // Если сравнение, подтвержденное указанным выше полем, корректно,
    // следующие 3 поля слияния возьмут данные из третьей строки.
    // В противном случае эти поля снова будут брать данные из строки 2.
    InsertMergeFields(builder, "Third row: ");

    doc.MailMerge.Execute(table);

     // В нашем источнике данных 3 строки, и мы дважды пропустили строки.
    // Наш выходной документ будет иметь 1 страницу с данными из всех 3-х строк.
    doc.Save(ArtifactsDir + "Field.NEXT.NEXTIF.docx");

/// <summary>
/// Использует построитель документов для вставки полей MERGEFIELD для источника данных, который содержит столбцы с именами "Courtesy Title", "First Name" и "Last Name".
/// </summary>
public void InsertMergeFields(DocumentBuilder builder, string firstFieldTextBefore)
{
    InsertMergeField(builder, "Courtesy Title", firstFieldTextBefore, " ");
    InsertMergeField(builder, "First Name", null, " ");
    InsertMergeField(builder, "Last Name", null, null);
    builder.InsertParagraph();
}

/// <summary>
/// Использует конструктор документов для вставки MERRGEFIELD с указанными свойствами.
/// </summary>
public void InsertMergeField(DocumentBuilder builder, string fieldName, string textBefore, string textAfter)
{
    FieldMergeField field = (FieldMergeField) builder.InsertField(FieldType.FieldMergeField, true);
    field.FieldName = fieldName;
    field.TextBefore = textBefore;
    field.TextAfter = textAfter;
}
```

### Смотрите также

* class [FieldNextIf](../)
* пространство имен [Aspose.Words.Fields](../../fieldnextif/)
* сборка [Aspose.Words](../../../)


