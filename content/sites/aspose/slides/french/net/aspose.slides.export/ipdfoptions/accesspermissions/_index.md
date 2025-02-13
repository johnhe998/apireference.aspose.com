---
title: AccessPermissions
second_title: Référence de l'API Aspose.Slides pour .NET
description: Contient un ensemble dindicateurs spécifiant les autorisations daccès à accorder lorsque le document est ouvert avec un accès utilisateur. VoirPdfAccessPermissionsaspose.slides.export/pdfaccesspermissions .
type: docs
weight: 10
url: /fr/net/aspose.slides.export/ipdfoptions/accesspermissions/
---
## IPdfOptions.AccessPermissions property

Contient un ensemble d'indicateurs spécifiant les autorisations d'accès à accorder lorsque le document est ouvert avec un accès utilisateur. Voir[`PdfAccessPermissions`](../../pdfaccesspermissions) .

```csharp
public PdfAccessPermissions AccessPermissions { get; set; }
```

### Exemples

```csharp
[C#]
var pdfOptions = new PdfOptions();
pdfOptions.Password = "my_password";
pdfOptions.AccessPermissions = PdfAccessPermissions.PrintDocument | PdfAccessPermissions.HighQualityPrint;

using (var presentation = new Presentation())
{
    presentation.Save(pdfFilePath, SaveFormat.Pdf, pdfOptions);
}
```

### Voir également

* enum [PdfAccessPermissions](../../pdfaccesspermissions)
* interface [IPdfOptions](../../ipdfoptions)
* espace de noms [Aspose.Slides.Export](../../ipdfoptions)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
