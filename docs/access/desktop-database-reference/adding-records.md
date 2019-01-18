---
title: 添加记录 （访问桌面数据库参考 （英文）
TOCTitle: Adding records
ms:assetid: 7a5b27bc-7b28-4f43-b55e-a21edfb9e1b3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249505(v=office.15)
ms:contentKeyID: 48545791
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 268cd381cdeef11f2a6f351160d930e4b169cfbf
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698839"
---
# <a name="adding-records"></a>添加记录

**适用于**： Access 2013、 Office 2013

使用 **AddNew** 方法在现有 **Recordset** 中创建并初始化新的记录。您可以使用 **Supports** 方法和 **adAddNew** 的 **CursorOptionEnum** 值来验证是否可以向当前 **Recordset** 对象添加记录。

在调用 **AddNew** 方法后，新记录会变为当前记录并在调用 **Update** 方法后仍然保持当前状态。如果 **Recordset** 对象不支持书签，则在转到其他记录后，您可能无法访问新记录。因此，根据游标类型，您可能希望调用 **Requery** 方法来使新记录可以访问。

如果在编辑当前记录或添加新记录时调用 **AddNew** ，则 ADO 会调用 **Update** 方法来保存所有更改，然后创建新记录。

本节包括下列主题：

- [添加多个字段](adding-multiple-fields.md)
- [确定编辑模式](determining-edit-mode.md)
- [在即时和批模式下使用 AddNew](using-addnew-in-immediate-and-batch-modes.md)

