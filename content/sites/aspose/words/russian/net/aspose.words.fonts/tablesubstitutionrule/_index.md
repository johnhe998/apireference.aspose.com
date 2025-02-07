---
title: Class TableSubstitutionRule
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fonts.TableSubstitutionRule сорт. Правило подстановки шрифта таблицы.
type: docs
weight: 2880
url: /ru/net/aspose.words.fonts/tablesubstitutionrule/
---
## TableSubstitutionRule class

Правило подстановки шрифта таблицы.

```csharp
public class TableSubstitutionRule : FontSubstitutionRule
```

## Характеристики

| Имя | Описание |
| --- | --- |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Указывает, включено ли правило. |

## Методы

| Имя | Описание |
| --- | --- |
| [AddSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/addsubstitutes/)(string, params string[]) | Добавляет замещающие имена шрифтов для заданного исходного имени шрифта. |
| [GetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/getsubstitutes/)(string) | Возвращает массив, содержащий замещающие имена шрифтов для указанного исходного имени шрифта. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load)(Stream) | Загружает настройки подстановки таблиц из потока XML. |
| [Load](../../aspose.words.fonts/tablesubstitutionrule/load/#load_1)(string) | Загружает настройки подстановки таблиц из файла XML. |
| [LoadAndroidSettings](../../aspose.words.fonts/tablesubstitutionrule/loadandroidsettings/)() | Загружает предопределенные параметры замены таблиц для платформы Linux. |
| [LoadLinuxSettings](../../aspose.words.fonts/tablesubstitutionrule/loadlinuxsettings/)() | Загружает предопределенные параметры замены таблиц для платформы Linux. |
| [LoadWindowsSettings](../../aspose.words.fonts/tablesubstitutionrule/loadwindowssettings/)() | Загружает предопределенные параметры подстановки таблиц для платформы Windows. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save)(Stream) | Сохраняет текущие настройки подстановки таблицы в поток. |
| [Save](../../aspose.words.fonts/tablesubstitutionrule/save/#save_1)(string) | Сохраняет текущие настройки подстановки таблиц в файл. |
| [SetSubstitutes](../../aspose.words.fonts/tablesubstitutionrule/setsubstitutes/)(string, params string[]) | Переопределить замещающие имена шрифтов для заданного исходного имени шрифта. |

### Примечания

Это правило определяет список имен шрифтов-заменителей, которые будут использоваться, если исходный шрифт недоступен.[`AltName`](../fontinfo/altname/) (если есть).

### Примеры

Показывает, как получить доступ к таблицам замены шрифтов для Windows и Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Создать новое правило подстановки таблиц и загрузить таблицу подстановки шрифтов Microsoft Windows по умолчанию.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// В Windows заменой по умолчанию для шрифта "Times New Roman CE" является "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Мы можем сохранить таблицу в виде XML-документа.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// В Linux есть собственная таблица подстановок.
// Существует несколько замещающих шрифтов для "Times New Roman CE".
// Если первая замена "FreeSerif" тоже недоступна,
// это правило будет циклически перебирать другие в массиве, пока не найдет доступное.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Сохраняем таблицу подстановок Linux в виде XML-документа с помощью потока.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Смотрите также

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* пространство имен [Aspose.Words.Fonts](../../aspose.words.fonts/)
* сборка [Aspose.Words](../../)


