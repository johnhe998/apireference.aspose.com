---
title: Class UserInformation
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fields.UserInformation сорт. Указывает информацию о пользователе.
type: docs
weight: 2610
url: /ru/net/aspose.words.fields/userinformation/
---
## UserInformation class

Указывает информацию о пользователе.

```csharp
public class UserInformation
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [UserInformation](userinformation/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| static [DefaultUser](../../aspose.words.fields/userinformation/defaultuser/) { get; } | Информация о пользователе по умолчанию. |
| [Address](../../aspose.words.fields/userinformation/address/) { get; set; } | Получает или задает почтовый адрес пользователя. |
| [Initials](../../aspose.words.fields/userinformation/initials/) { get; set; } | Получает или задает инициалы пользователя. |
| [Name](../../aspose.words.fields/userinformation/name/) { get; set; } | Получает или задает имя пользователя. |

### Примеры

Показывает, как установить сведения о пользователе и отобразить их с помощью полей.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте объект UserInformation и установите его в качестве источника данных для полей, отображающих информацию о пользователе.
UserInformation userInformation = new UserInformation
{
    Name = "John Doe",
    Initials = "J. D.",
    Address = "123 Main Street"
};
doc.FieldOptions.CurrentUser = userInformation;

// Вставляем поля USERNAME, USERINITIALS и USERADDRESS, которые отображают значения
// соответствующие свойства объекта UserInformation, который мы создали выше. 
Assert.AreEqual(userInformation.Name, builder.InsertField(" USERNAME ").Result);
Assert.AreEqual(userInformation.Initials, builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual(userInformation.Address, builder.InsertField(" USERADDRESS ").Result);

// Объект параметров поля также имеет статического пользователя по умолчанию, на которого могут ссылаться поля из всех документов.
UserInformation.DefaultUser.Name = "Default User";
UserInformation.DefaultUser.Initials = "D. U.";
UserInformation.DefaultUser.Address = "One Microsoft Way";
doc.FieldOptions.CurrentUser = UserInformation.DefaultUser;

Assert.AreEqual("Default User", builder.InsertField(" USERNAME ").Result);
Assert.AreEqual("D. U.", builder.InsertField(" USERINITIALS ").Result);
Assert.AreEqual("One Microsoft Way", builder.InsertField(" USERADDRESS ").Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.CurrentUser.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Fields](../../aspose.words.fields/)
* сборка [Aspose.Words](../../)


