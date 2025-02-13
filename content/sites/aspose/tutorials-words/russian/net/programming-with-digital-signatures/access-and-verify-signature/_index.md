---
title: Доступ и проверка подписи в документе Word
linktitle: Доступ и проверка подписи в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить доступ и проверить цифровые подписи в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-digital-signatures/access-and-verify-signature/
---
В этом руководстве мы покажем вам, как использовать функцию проверки доступа и подписи Aspose.Words для .NET. Эта функция позволяет получить доступ к цифровым подписям в документе Word и проверить их действительность. Выполните следующие действия:

## Шаг 1. Загрузка документа и доступ к подписям

Начните с загрузки документа, содержащего цифровые подписи:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Шаг 2. Просмотр цифровых подписей

Используйте цикл для перебора всех цифровых подписей в документе:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Доступ к информации о подписи
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Это свойство доступно только в документах MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Обязательно настройте отображаемые сообщения в соответствии с вашими потребностями.

### Пример исходного кода для доступа и проверки подписи с использованием Aspose.Words для .NET

Вот полный исходный код для проверки доступа и подписи с использованием Aspose.Words для .NET:

```csharp
	
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Это свойство доступно только в документах MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Выполнив эти шаги, вы сможете легко получить доступ и проверить цифровые подписи в документе Word с помощью Aspose.Words для .NET.

## Заключение

В этом руководстве мы рассмотрели функцию доступа и проверки цифровых подписей в документе Word с помощью Aspose.Words для .NET. Следуя приведенным инструкциям, вы можете легко загрузить документ, получить доступ к его цифровым подписям и проверить их действительность. Возможность доступа и проверки цифровых подписей позволяет гарантировать целостность и подлинность ваших документов Word. Aspose.Words for .NET предлагает мощный API для обработки текстов с цифровыми подписями, позволяющий автоматизировать процесс проверки и повысить безопасность ваших документов.

### Часто задаваемые вопросы

#### В: Что такое цифровые подписи в документе Word?

О: Цифровые подписи в документе Word — это электронные подписи, которые позволяют удостоверить подлинность и подлинность документа. Они создаются с использованием цифровых сертификатов и криптографических алгоритмов, что позволяет получателям убедиться, что документ не был изменен и получен из надежного источника.

#### В: Как я могу получить доступ к цифровым подписям в документе Word, используя Aspose.Words для .NET?

О: Чтобы получить доступ к цифровым подписям в документе Word с помощью Aspose.Words for .NET, выполните следующие действия:
1.  Загрузите документ с помощью`Document` class и указать путь к файлу документа.
2.  Используйте цикл для перебора`DigitalSignatures` сбор документа. Каждая итерация представляет собой цифровую подпись.

#### В: К какой информации я могу получить доступ из цифровой подписи в документе Word?

О: Из цифровой подписи в документе Word вы можете получить доступ к различной информации, например:
- Действительность: проверьте, действительна ли подпись.
- Комментарии: Получите причину подписания, указанную подписывающей стороной.
- Время подписания: Узнайте время подписания документа.
- Имя субъекта: Получите имя подписавшего или субъекта сертификата.
- Имя издателя: Получите имя издателя сертификата.

#### В: Могу ли я проверить действительность цифровой подписи в документе Word с помощью Aspose.Words for .NET?

 О: Да, вы можете проверить действительность цифровой подписи в документе Word с помощью Aspose.Words for .NET. Получив доступ к`IsValid`собственность`DigitalSignature` объект, вы можете определить, действительна ли подпись или нет.

#### В: Как я могу проверить подлинность цифровых подписей в документе Word с помощью Aspose.Words for .NET?

О: Чтобы проверить действительность цифровых подписей в документе Word с помощью Aspose.Words for .NET, вы можете выполнить следующие действия:
1.  Доступ к`DigitalSignatures` сбор документа.
2.  Итерация через каждый`DigitalSignature` объект в коллекции.
3.  Использовать`IsValid`собственность`DigitalSignature` object для проверки правильности подписи.

#### В: Могу ли я получить комментарии подписывающей стороны или причину подписания из цифровой подписи в документе Word?

О: Да, вы можете получить комментарии подписывающей стороны или причину подписания из цифровой подписи в документе Word.`Comments`собственность`DigitalSignature` Объект предоставляет доступ к комментариям, указанным подписывающей стороной в процессе подписания.

#### В: Какие типы документов поддерживает функция проверки подписи в Aspose.Words для .NET?

О: Функция проверки подписи в Aspose.Words для .NET поддерживает проверку цифровых подписей в документах Word с файловым форматом DOCX. Вы можете использовать эту функцию для проверки подписей в файлах DOCX.

#### Вопрос. Как получить доступ к сведениям о сертификате цифровой подписи в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы получить доступ к сведениям о сертификате цифровой подписи в документе Word с помощью Aspose.Words for .NET, вы можете получить доступ к`CertificateHolder`собственность`DigitalSignature` объект. Из`CertificateHolder` объект, вы можете получить различные сведения о сертификате, такие как имя субъекта и имя издателя.

#### В: Могу ли я настроить отображение или обработку цифровых подписей в документе Word с помощью Aspose.Words for .NET?

 О: Да, вы можете настроить отображение или обработку цифровых подписей в документе Word с помощью Aspose.Words for .NET. Получив доступ к свойствам и методам`DigitalSignature` объект, вы можете извлечь нужную информацию, выполнить дополнительные проверки или интегрировать процесс проверки подписи в рабочий процесс вашего приложения.

#### В: Можно ли проверить несколько цифровых подписей в документе Word с помощью Aspose.Words для .NET?

 О: Да, можно проверить несколько цифровых подписей в документе Word с помощью Aspose.Words для .NET. Итерируя через`DigitalSignatures` коллекции документа, вы можете получить доступ и проверить каждую цифровую подпись по отдельности.

