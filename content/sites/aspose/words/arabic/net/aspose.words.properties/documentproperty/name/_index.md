---
title: DocumentProperty.Name
second_title: Aspose.Words لمراجع .NET API
description: DocumentProperty ملكية. إرجاع اسم الخاصية.
type: docs
weight: 30
url: /ar/net/aspose.words.properties/documentproperty/name/
---
## DocumentProperty.Name property

إرجاع اسم الخاصية.

```csharp
public string Name { get; }
```

### ملاحظات

لا يمكن أن تكون خالية ولا يمكن أن تكون سلسلة فارغة.

### أمثلة

يوضح كيفية العمل بخصائص المستند المضمنة.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// يحتوي كائن "المستند" على بعض بيانات التعريف الخاصة به في أعضائه.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// يخزن المستند أيضًا البيانات الوصفية في خصائصه المضمنة.
// كل خاصية مضمنة هي عضو في كائن "BuiltInDocumentProperties" للمستند.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // قد تخزن بعض الخصائص قيمًا متعددة.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### أنظر أيضا

* class [DocumentProperty](../)
* مساحة الاسم [Aspose.Words.Properties](../../documentproperty/)
* المجسم [Aspose.Words](../../../)


