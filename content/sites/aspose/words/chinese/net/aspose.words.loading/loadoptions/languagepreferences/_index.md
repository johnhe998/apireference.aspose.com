---
title: LoadOptions.LanguagePreferences
second_title: Aspose.Words for .NET API 参考
description: LoadOptions 财产. 获取加载文档时将使用的语言首选项
type: docs
weight: 80
url: /zh/net/aspose.words.loading/loadoptions/languagepreferences/
---
## LoadOptions.LanguagePreferences property

获取加载文档时将使用的语言首选项。

```csharp
public LanguagePreferences LanguagePreferences { get; }
```

### 例子

显示如何在加载文档时应用语言首选项。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### 也可以看看

* class [LanguagePreferences](../../languagepreferences/)
* class [LoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../loadoptions/)
* 部件 [Aspose.Words](../../../)


