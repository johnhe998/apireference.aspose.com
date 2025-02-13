---
title: IHyphenationCallback.RequestDictionary
second_title: Справочник по API Aspose.Words для .NET
description: IHyphenationCallback метод. Уведомляет приложение о том что словарь переносов для указанного языка не найден и возможно его необходимо зарегистрировать.
type: docs
weight: 10
url: /ru/net/aspose.words/ihyphenationcallback/requestdictionary/
---
## IHyphenationCallback.RequestDictionary method

Уведомляет приложение о том, что словарь переносов для указанного языка не найден и, возможно, его необходимо зарегистрировать.

Реализация должна найти словарь и зарегистрировать его с помощью[`RegisterDictionary`](../../hyphenation/registerdictionary/)методы.

Если словарь недоступен для указанной реализации языка, можно отказаться от дальнейших вызовов для того же языка с помощью[`RegisterDictionary`](../../hyphenation/registerdictionary/) с нулевым значением.

```csharp
public void RequestDictionary(string language)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| language | String | Название языка, например "en-US". См. документацию .NET для «имени культуры» и RFC 4646 для получения подробной информации. |

### Примечания

Исключения, создаваемые этим методом, прервут выполнение процесса макета страницы.

### Примеры

Показывает, как открыть и зарегистрировать словарь из файла.

```csharp
{
    // Настраиваем обратный вызов, который отслеживает предупреждения, возникающие при регистрации словаря переносов.
    WarningInfoCollection warningInfoCollection = new WarningInfoCollection();
    Hyphenation.WarningCallback = warningInfoCollection;

    // Зарегистрировать английский (США) словарь переносов по потоку.
    Stream dictionaryStream = new FileStream(MyDir + "hyph_en_US.dic", FileMode.Open);
    Hyphenation.RegisterDictionary("en-US", dictionaryStream);

    Assert.AreEqual(0, warningInfoCollection.Count);

    // Откройте документ с языковым стандартом, в котором Microsoft Word не может использовать дефис на англоязычном компьютере, например немецком.
    Document doc = new Document(MyDir + "German text.docx");

    // Чтобы расставлять переносы в этом документе при сохранении, нам нужен словарь переносов для языкового кода "de-CH".
    // Этот обратный вызов будет обрабатывать автоматический запрос для этого словаря.
    Hyphenation.Callback = new CustomHyphenationDictionaryRegister();

    // Когда мы сохраним документ, немецкие переносы вступят в силу.
    doc.Save(ArtifactsDir + "Hyphenation.RegisterDictionary.pdf");

    // Этот словарь содержит два одинаковых шаблона, которые вызовут предупреждение.
    Assert.AreEqual(1, warningInfoCollection.Count);
    Assert.AreEqual(WarningType.MinorFormattingLoss, warningInfoCollection[0].WarningType);
    Assert.AreEqual(WarningSource.Layout, warningInfoCollection[0].Source);
    Assert.AreEqual("Hyphenation dictionary contains duplicate patterns. The only first found pattern will be used. " +
                    "Content can be wrapped differently.", warningInfoCollection[0].Description);
}

/// <summary>
/// Связывает языковые коды ISO с именами файлов локальной системы для файлов словарей расстановки переносов.
/// </summary>
private class CustomHyphenationDictionaryRegister : IHyphenationCallback
{
    public CustomHyphenationDictionaryRegister()
    {
        mHyphenationDictionaryFiles = new Dictionary<string, string>
        {
            { "en-US", MyDir + "hyph_en_US.dic" },
            { "de-CH", MyDir + "hyph_de_CH.dic" }
        };
    }

    public void RequestDictionary(string language)
    {
        Console.Write("Hyphenation dictionary requested: " + language);

        if (Hyphenation.IsDictionaryRegistered(language))
        {
            Console.WriteLine(", is already registered.");
            return;
        }

        if (mHyphenationDictionaryFiles.ContainsKey(language))
        {
            Hyphenation.RegisterDictionary(language, mHyphenationDictionaryFiles[language]);
            Console.WriteLine(", successfully registered.");
            return;
        }

        Console.WriteLine(", no respective dictionary file known by this Callback.");
    }

    private readonly Dictionary<string, string> mHyphenationDictionaryFiles;
}
```

### Смотрите также

* interface [IHyphenationCallback](../)
* пространство имен [Aspose.Words](../../ihyphenationcallback/)
* сборка [Aspose.Words](../../../)


