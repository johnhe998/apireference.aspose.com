---
title: License.License
second_title: Référence de l'API Aspose.Words pour .NET
description: License constructeur. Initialise une nouvelle instance de cette classe.
type: docs
weight: 10
url: /fr/net/aspose.words/license/license/
---
## License constructor

Initialise une nouvelle instance de cette classe.

```csharp
public License()
```

### Exemples

Montre comment initialiser une licence pour Aspose.Words à l'aide d'un fichier de licence dans le système de fichiers local.

```csharp
// Définissez la licence de notre produit Aspose.Words en transmettant le nom de fichier du système de fichiers local d'un fichier de licence valide.
string licenseFileName = Path.Combine(LicenseDir, "Aspose.Words.NET.lic");

License license = new License();
license.SetLicense(licenseFileName);

// Créez une copie de notre fichier de licence dans le dossier des binaires de notre application.
string licenseCopyFileName = Path.Combine(AssemblyDir, "Aspose.Words.NET.lic");
File.Copy(licenseFileName, licenseCopyFileName);

// Si on passe le nom d'un fichier sans chemin,
// SetLicense recherchera ce fichier dans plusieurs emplacements du système de fichiers local.
// L'un de ces emplacements sera le dossier "bin", qui contient une copie de notre fichier de licence.
license.SetLicense("Aspose.Words.NET.lic");
```

### Voir également

* class [License](../)
* espace de noms [Aspose.Words](../../license/)
* Assemblée [Aspose.Words](../../../)


