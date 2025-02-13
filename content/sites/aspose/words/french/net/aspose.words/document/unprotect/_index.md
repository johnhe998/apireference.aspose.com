---
title: Document.Unprotect
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Supprime la protection du document quel que soit le mot de passe.
type: docs
weight: 720
url: /fr/net/aspose.words/document/unprotect/
---
## Unprotect() {#unprotect_1}

Supprime la protection du document quel que soit le mot de passe.

```csharp
public void Unprotect()
```

### Remarques

Cette méthode déprotège le document même s'il a un mot de passe de protection.

Notez que la protection du document est différente de la protection en écriture. La protection en écriture est spécifiée à l'aide de la[`WriteProtection`](../writeprotection/).

### Exemples

Montre comment protéger et déprotéger un document.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Si nous ouvrons ce document avec Microsoft Word dans l'intention de le modifier,
// nous devrons appliquer le mot de passe pour passer la protection.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Notez que la protection ne s'applique qu'aux utilisateurs de Microsoft Word ouvrant notre document.
// Nous n'avons en aucun cas chiffré le document et nous n'avons pas besoin du mot de passe pour l'ouvrir et le modifier par programme.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Il existe deux manières de supprimer la protection d'un document.
// 1 - Sans mot de passe :
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - Avec le bon mot de passe :
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)

---

## Unprotect(string) {#unprotect}

Supprime la protection du document si un mot de passe correct est spécifié.

```csharp
public bool Unprotect(string password)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| password | String | Le mot de passe avec lequel déprotéger le document. |

### Return_Value

Vrai si un mot de passe correct a été spécifié et que le document n'était pas protégé.

### Remarques

Cette méthode déprotège le document uniquement si un mot de passe correct est spécifié.

Notez que la protection du document est différente de la protection en écriture. La protection en écriture est spécifiée à l'aide de la[`WriteProtection`](../writeprotection/).

### Exemples

Montre comment protéger et déprotéger un document.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Si nous ouvrons ce document avec Microsoft Word dans l'intention de le modifier,
// nous devrons appliquer le mot de passe pour passer la protection.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Notez que la protection ne s'applique qu'aux utilisateurs de Microsoft Word ouvrant notre document.
// Nous n'avons en aucun cas chiffré le document et nous n'avons pas besoin du mot de passe pour l'ouvrir et le modifier par programme.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Il existe deux manières de supprimer la protection d'un document.
// 1 - Sans mot de passe :
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - Avec le bon mot de passe :
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


