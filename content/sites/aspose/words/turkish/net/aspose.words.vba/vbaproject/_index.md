---
title: Class VbaProject
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Vba.VbaProject sınıf. VBA proje bilgilerine erişim sağlar. Belge içindeki bir VBA projesi VBA modüllerinin bir koleksiyonu olarak tanımlanır.
type: docs
weight: 6270
url: /tr/net/aspose.words.vba/vbaproject/
---
## VbaProject class

VBA proje bilgilerine erişim sağlar. Belge içindeki bir VBA projesi, VBA modüllerinin bir koleksiyonu olarak tanımlanır.

```csharp
public class VbaProject
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [VbaProject](vbaproject/)() | Boş bir VbaProject oluşturur. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [CodePage](../../aspose.words.vba/vbaproject/codepage/) { get; } | VBA projesinin kod sayfasını döndürür. |
| [IsSigned](../../aspose.words.vba/vbaproject/issigned/) { get; } | VbaProject'in imzalanıp imzalanmadığını gösterir. |
| [Modules](../../aspose.words.vba/vbaproject/modules/) { get; } | VBA proje modüllerinin koleksiyonunu döndürür. |
| [Name](../../aspose.words.vba/vbaproject/name/) { get; set; } | VBA proje adını alır veya ayarlar. |
| [References](../../aspose.words.vba/vbaproject/references/) { get; } | VBA proje başvurularının bir koleksiyonunu alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Clone](../../aspose.words.vba/vbaproject/clone/)() | `VbaProject` . |

### Örnekler

Bir belgenin VBA proje bilgilerine nasıl erişileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Bir VBA projesi, bir VBA modülleri koleksiyonu içerir.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// VBA modülü için yeni kaynak kodu ayarlayın. Koleksiyondaki VBA modüllerine dizine veya ada göre erişebilirsiniz.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Koleksiyondan bir modülü kaldırın.
vbaModules.Remove(vbaModules[2]);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Vba](../../aspose.words.vba/)
* toplantı [Aspose.Words](../../)


