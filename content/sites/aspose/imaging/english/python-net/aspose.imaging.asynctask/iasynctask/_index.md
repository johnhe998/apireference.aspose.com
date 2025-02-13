---
title: IAsyncTask Class
type: docs
weight: 30
url: /python-net/aspose.imaging.asynctask/iasynctask/
---

The asynchronous task.

**Module:** [aspose.imaging.asynctask](/imaging/python-net/aspose.imaging.asynctask/)

**Full Name:** aspose.imaging.asynctask.IAsyncTask

**Aspose.Imaging Version:** 23.6

The IAsyncTask type exposes the following members:
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| is_busy | bool | r | Gets a value indicating whether this task is currently running. |
| is_canceled | bool | r | Gets a value indicating whether this task was canceled. |
| is_faulted | bool | r | Gets a value indicating whether this task was faulted. |
| result | object | r | Gets the result of this task. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| run_async() | Runs this task. |
| cancel() | Cancels this task.<br/>            The task is completed safely by the controlled stopping of the algorithm. |
| abort() | Aborts this task.<br/>            The task is completed immediately, with the risk of not freeing internal unmanaged resources. |
| wait_on_done() | Waits until task is finished. |

