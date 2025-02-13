---
title: Class License
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.License сорт. Предоставляет методы лицензирования компонента.
type: docs
weight: 3220
url: /ru/net/aspose.words/license/
---
## License class

Предоставляет методы лицензирования компонента.

```csharp
public class License
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [License](license/)() | Инициализирует новый экземпляр этого класса. |

## Методы

| Имя | Описание |
| --- | --- |
| [SetLicense](../../aspose.words/license/setlicense/#setlicense)(Stream) | Лицензирует компонент. |
| [SetLicense](../../aspose.words/license/setlicense/#setlicense_1)(string) | Лицензирует компонент. |

### Примеры

Показывает, как инициализировать лицензию для Aspose.Words, используя файл лицензии в локальной файловой системе.

```csharp
// Установите лицензию для нашего продукта Aspose.Words, передав имя файла локальной файловой системы действительного файла лицензии.
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// Создаем копию нашего файла лицензии в папке бинарных файлов нашего приложения.
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// Если мы передаем имя файла без пути,
// SetLicense будет искать этот файл в нескольких местах локальной файловой системы.
// Одним из таких мест будет папка «bin», содержащая копию нашего файла лицензии.
license.SetLicense("Aspose.Words.NET.lic");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


