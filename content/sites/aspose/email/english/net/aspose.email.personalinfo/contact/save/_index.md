---
title: Contact.Save
second_title: Aspose.Email for .NET API Reference
description: Contact method. Saves this MapiContact into the given stream with vCard format. The supported vCard version is 2.1
type: docs
weight: 410
url: /net/aspose.email.personalinfo/contact/save/
---
## Save(Stream) {#save}

Saves this [`MapiContact`](../../../aspose.email.mapi/mapicontact/) into the given stream with vCard format. The supported vCard version is 2.1

```csharp
public void Save(Stream stream)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | A stream to save to |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | *stream* is `null` |
| NotSupportedException | *stream* does not support writing |

### See Also

* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)

---

## Save(string) {#save_3}

Saves this [`MapiContact`](../../../aspose.email.mapi/mapicontact/) to the vCard file with a default options. The supported vCard version is 2.1

```csharp
public void Save(string filePath)
```

| Parameter | Type | Description |
| --- | --- | --- |
| filePath | String | A vCard file name |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentException | *filePath* is `null` or `empty` |

### See Also

* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)

---

## Save(string, ContactSaveOptions) {#save_5}

Saves this [`MapiContact`](../../../aspose.email.mapi/mapicontact/) into file using specified save options. The supported save options is [`VCardSaveOptions`](../../../aspose.email.personalinfo.vcard/vcardsaveoptions/)

```csharp
public void Save(string filePath, ContactSaveOptions saveOptions)
```

| Parameter | Type | Description |
| --- | --- | --- |
| filePath | String | A vCard file name |
| saveOptions | ContactSaveOptions | A save options |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentException | *filePath* is `null` or `empty` |
| ArgumentNullException | *saveOptions* is `null` |
| NotSupportedException | some save option is not supported |

### See Also

* class [ContactSaveOptions](../../../aspose.email.mapi/contactsaveoptions/)
* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)

---

## Save(string, ContactSaveFormat) {#save_4}

Saves this [`MapiContact`](../../../aspose.email.mapi/mapicontact/) to the specified file with a format using the default options. The supported save format is vCard.

```csharp
public void Save(string filePath, ContactSaveFormat saveFormat)
```

| Parameter | Type | Description |
| --- | --- | --- |
| filePath | String | A vCard file name |
| saveFormat | ContactSaveFormat | A save format |

### See Also

* enum [ContactSaveFormat](../../../aspose.email.mapi/contactsaveformat/)
* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)

---

## Save(Stream, ContactSaveFormat) {#save_1}

Saves this [`Contact`](../) to the given stream with a format using the default options.

```csharp
public void Save(Stream stream, ContactSaveFormat saveFormat)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | A stream to save to |
| saveFormat | ContactSaveFormat | A save format |

### See Also

* enum [ContactSaveFormat](../../../aspose.email.mapi/contactsaveformat/)
* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)

---

## Save(Stream, ContactSaveOptions) {#save_2}

Saves this [`Contact`](../) to the given stream using specified save options.

```csharp
public void Save(Stream stream, ContactSaveOptions saveOptions)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | A stream to save to |
| saveOptions | ContactSaveOptions | A save options |

### See Also

* class [ContactSaveOptions](../../../aspose.email.mapi/contactsaveoptions/)
* class [Contact](../)
* namespace [Aspose.Email.PersonalInfo](../../contact/)
* assembly [Aspose.Email](../../../)


