---
title: CursorLocation 属性 (ADO)
TOCTitle: CursorLocation property (ADO)
ms:assetid: 8a048bd4-ae25-a555-1c07-14364b7e6560
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249606(v=office.15)
ms:contentKeyID: 48546182
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 25fd81acee3c541c8a3f315f96fa69241272a655
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295218"
---
# <a name="cursorlocation-property-ado"></a>CursorLocation 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示游标服务的位置。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，该值可以设置为 [CursorLocationEnum](cursorlocationenum.md) 值之一。

## <a name="remarks"></a>注解

此属性允许在提供程序可访问的各种游标库间进行选择。通常，可以选择使用客户端游标库或位于服务器上的游标库。

此属性设置仅影响在设置了该属性后建立的连接。更改 **CursorLocation** 属性对现有的连接没有影响。

[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection) 方法返回的游标将继承此设置。 **Recordset** 对象将从其关联的连接自动继承此设置。

此属性在 [Connection](connection-object-ado.md) 或已关闭的 [Recordset](recordset-object-ado.md) 上为可读/写属性，而在打开的 **Recordset** 上为只读属性。

**远程数据服务使用情况**在客户端**Recordset**或**Connection**对象上使用时, **CursorLocation**属性仅可设置为**adUseClient**。

