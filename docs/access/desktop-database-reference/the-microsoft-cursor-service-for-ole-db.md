---
title: Microsoft Cursor Service for OLE DB
TOCTitle: The Microsoft Cursor Service for OLE DB
ms:assetid: 31861eef-9860-c884-3c60-9794def7be78
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249088(v=office.15)
ms:contentKeyID: 48544057
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ce8ebea2e9ce1f31adc239195614f4a8b1e2bd1b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722618"
---
# <a name="microsoft-cursor-service-for-ole-db"></a>用于 OLE DB 的 Microsoft 游标服务


**适用于**： Access 2013、 Office 2013

当选择客户端游标时，或将 **CursorLocation** 属性设置为 **adUseClient** 时，就激活了 Microsoft Cursor Service for OLE DB。您还可能看到"客户端游标引擎"的参考，该参考实际上与 ADO 上下文中的内容是相同的。此服务补充了数据提供程序的游标支持功能。这样，您就可以理解所有数据提供程序的相对统一的功能。

Cursor Service for OLE DB 使得动态属性变为可用，并增强了某些方法的行为。例如，利用 **Optimize** 动态属性可以创建临时索引以简化某些操作，如 **Find** 方法。

在所有情况下，Cursor Service 都支持批更新。此外，如果数据提供程序只能提供功能不太强的游标（如静态游标），Cursor Service 还可以模拟功能较强的游标类型（如动态游标）。

