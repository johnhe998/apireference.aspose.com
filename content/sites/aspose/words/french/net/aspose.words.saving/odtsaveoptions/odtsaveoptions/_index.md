---
title: OdtSaveOptions.OdtSaveOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: OdtSaveOptions constructeur. Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer un document dans leOdt format.
type: docs
weight: 10
url: /fr/net/aspose.words.saving/odtsaveoptions/odtsaveoptions/
---
## OdtSaveOptions() {#constructor}

Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer un document dans leOdt format.

```csharp
public OdtSaveOptions()
```

### Exemples

Montre comment rendre un document enregistré conforme à un ancien schéma ODT.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Voir également

* class [OdtSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../odtsaveoptions/)
* Assemblée [Aspose.Words](../../../)

---

## OdtSaveOptions(string) {#constructor_2}

Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer un document dans leOdt format crypté avec un mot de passe.

```csharp
public OdtSaveOptions(string password)
```

### Voir également

* class [OdtSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../odtsaveoptions/)
* Assemblée [Aspose.Words](../../../)

---

## OdtSaveOptions(SaveFormat) {#constructor_1}

Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer un document dans leOdt ou Ott format.

```csharp
public OdtSaveOptions(SaveFormat saveFormat)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| saveFormat | SaveFormat | Peut êtreOdt ouOtt. |

### Exemples

Montre comment chiffrer un document ODT/OTT enregistré avec un mot de passe, puis le charger à l'aide de Aspose.Words.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Crée un nouveau OdtSaveOptions, et passe soit "SaveFormat.Odt",
// ou "SaveFormat.Ott" comme format d'enregistrement du document. 
OdtSaveOptions saveOptions = new OdtSaveOptions(saveFormat);
saveOptions.Password = "@sposeEncrypted_1145";

string extensionString = FileFormatUtil.SaveFormatToExtension(saveFormat);

// Si nous ouvrons ce document avec un éditeur approprié,
// il nous demandera le mot de passe que nous avons spécifié dans l'objet SaveOptions.
doc.Save(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString, saveOptions);

FileFormatInfo docInfo = FileFormatUtil.DetectFileFormat(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString);

Assert.IsTrue(docInfo.IsEncrypted);

// Si nous souhaitons ouvrir ou modifier à nouveau ce document en utilisant Aspose.Words,
// nous devrons fournir un objet LoadOptions avec le mot de passe correct au constructeur de chargement.
doc = new Document(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString,
    new LoadOptions("@sposeEncrypted_1145"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Voir également

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [OdtSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../odtsaveoptions/)
* Assemblée [Aspose.Words](../../../)


