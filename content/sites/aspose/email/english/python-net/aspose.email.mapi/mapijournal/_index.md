---
title: MapiJournal
second_title: Aspose.Email for Python via .NET API Reference
description: 
type: docs
weight: 530
url: /python-net/aspose.email.mapi/mapijournal/
---

## MapiJournal class

Represents the Outlook Journal object.

The MapiJournal type exposes the following members:
## Constructors
| Name | Description |
| :- | :- |
|MapiJournal()|Initializes a new instance of the [MapiJournal](/email/python-net/aspose.email.mapi/mapijournal/) class.|
|MapiJournal(subject, body, description, brief_description)|Initializes a new instance of the MapiJournal class|
## Properties
| Name | Description |
| :- | :- |
|properties|  |
|code_page|  |
|item_id|The item id, uses with a server|
|attachments|Gets the attachments in the message.|
|property_stream|Gets the property stream.|
|named_properties|Gets the named properties of message.|
|recipients|Gets the recipients of the message.|
|sub_storages|Gets the sub storages.|
|named_property_mapping|Gets the named property mapping.|
|subject_prefix|Gets a subject prefix that typically indicates some action on a message, such as "FW: " for forwarding.|
|body_type|Gets the type of the body.|
|body_rtf|Gets or sets the RTF formatted message text.|
|body_html|Gets the [body_rtf](/email/python-net/aspose.email.mapi/mapimessageitembase/) of the message converted to HTML, if present, otherwise an empty string.|
|companies|Contains the names of the companies that are associated with an item.|
|categories|Contains keywords or categories for the message object.|
|mileage|Contains the mileage information that is associated with an item.|
|billing|Contains the billing information associated with an item.|
|sensitivity|Gets the Sensitivity.|
|message_class|Gets a case-sensitive string that identifies the sender-defined message class, such as IPM.Note.<br/>            The message class specifies the type, purpose, or content of the message.|
|supported_type|Gets the supported item type.|
|body|Gets the message text.|
|subject|Gets or sets the subject of the message.|
|brief_description|Gets or sets the brief description <br/>            of activity that is being recorded.|
|description|Gets or sets the description <br/>            of activity that is being recorded.|
|start_time|Gets or sets the time at which the activity began.|
|end_time|Gets or sets the time at which the activity ended.|
|duration|Gets the duration of the activity.|
|document_status|Gets or sets the status of document.|
|flags|Gets or sets a flags that contains metadata <br/>            about the Journal object.|
## Methods
| Name | Description |
| :- | :- |
|set_property(pd, value)|  |
|set_property(value)|  |
|try_get_property_string(tag, codepage)|  |
|try_get_property_string(tag)|  |
|try_get_property_string(tag, value, codepage)|  |
|try_get_property_string(tag, value)|  |
|get_property_string(tag, codepage)|  |
|get_property_string(tag)|  |
|set_body_content(content, content_type)|  |
|set_body_content(content, content_type, compression)|  |
|save(file_name)|  |
|save(stream)|  |
|get_property(pd)|  |
|try_get_property_data(tag)|  |
|get_property_bytes(tag)|  |
|get_property_int32(tag)|  |
|get_property_long(tag)|  |
|get_property_short(tag)|  |
|get_property_boolean(tag)|  |
|get_property_date_time(key)|  |
|is_store_unicode_ok()|  |
|try_get_property_date_time(tag, value)|  |
|try_get_property_long(tag, value)|  |
|try_get_property_int32(tag, value)|  |
|set_body_rtf(content, compression)|  |
|set_message_flags(flags)|  |
|remove_property(tag)|  |

### See Also

* namespace [aspose.email.mapi](/email/python-net/aspose.email.mapi/)
* assembly [Aspose.Email](/email/python-net/)

