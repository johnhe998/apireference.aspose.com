---
title: Document.CompatibilityOptions
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Предоставляет доступ к параметрам совместимости документов то есть к настройкам пользователя введенным на Совместимость вкладка Опции диалоговое окно в Word.
type: docs
weight: 50
url: /ru/net/aspose.words/document/compatibilityoptions/
---
## Document.CompatibilityOptions property

Предоставляет доступ к параметрам совместимости документов (то есть к настройкам пользователя, введенным на **Совместимость** вкладка **Опции** диалоговое окно в Word).

```csharp
public CompatibilityOptions CompatibilityOptions { get; }
```

### Примеры

Показывает, как оптимизировать документ для разных версий Microsoft Word.

```csharp
public void OptimizeFor()
{
    Document doc = new Document();

    // Этот объект содержит обширный список флагов, уникальных для каждого документа
    // которые позволяют нам обеспечить обратную совместимость со старыми версиями Microsoft Word.
    CompatibilityOptions options = doc.CompatibilityOptions;

    // Печать настроек по умолчанию для пустого документа.
    Console.WriteLine("\nDefault optimization settings:");
    PrintCompatibilityOptions(options);

    // Мы можем получить доступ к этим настройкам в Microsoft Word через «Файл» -> "Опции" -> «Дополнительно» -> "Параметры совместимости для...".
    doc.Save(ArtifactsDir + "CompatibilityOptions.OptimizeFor.DefaultSettings.docx");

    // Мы можем использовать метод OptimizeFor, чтобы обеспечить оптимальную совместимость с определенной версией Microsoft Word.
    doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
    Console.WriteLine("\nOptimized for Word 2010:");
    PrintCompatibilityOptions(options);

    doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2000);
    Console.WriteLine("\nOptimized for Word 2000:");
    PrintCompatibilityOptions(options);
}

/// <summary>
/// Группирует все флаги в объекте параметров совместимости документа по состоянию, а затем печатает каждую группу.
/// </summary>
private static void PrintCompatibilityOptions(CompatibilityOptions options)
{
    for (int i = 1; i >= 0; i--)
    {
        Console.WriteLine(Convert.ToBoolean(i) ? "\tEnabled options:" : "\tDisabled options:");
        SortedSet<string> optionNames = new SortedSet<string>();

        foreach (System.ComponentModel.PropertyDescriptor descriptor in System.ComponentModel.TypeDescriptor.GetProperties(options))
        {
            if (descriptor.PropertyType == Type.GetType("System.Boolean") && i == Convert.ToInt32(descriptor.GetValue(options)))
            {
                optionNames.Add(descriptor.Name);
            }
        }

        foreach (string s in optionNames)
        {
            Console.WriteLine($"\t\t{s}");
        }
    }
}
```

### Смотрите также

* class [CompatibilityOptions](../../../aspose.words.settings/compatibilityoptions/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


