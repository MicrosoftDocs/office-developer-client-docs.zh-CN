---
title: 与记录集相关的错误信息
TOCTitle: Recordset-related error information
ms:assetid: 388308c7-e121-bd12-228a-312c897b8c55
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249136(v=office.15)
ms:contentKeyID: 48544222
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 12a67657d5543aac22a49690256b0410a2b901bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307614"
---
# <a name="recordset-related-error-information"></a>与记录集相关的错误信息

**适用于**：Access 2013、Office 2013

在批处理期间，**Recordset** 对象的 **Status** 属性将提供 **Recordset** 中各个记录的信息。 发生批更新之前，**Recordset** 的 **Status** 属性可以反映将要添加、更改和删除的记录的相关信息。 

调用 **UpdateBatch** 之后，**Status** 属性将指示操作成功或失败。 在 **Recordset** 中从一条记录移动到另一条记录时，**Status** 属性的值将发生更改，以描述当前记录的状态。

