---
title: IsolationLevel 属性 (ADO)
TOCTitle: IsolationLevel property (ADO)
ms:assetid: 19461be5-c94b-4b61-ce08-7abdf702c3dc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248939(v=office.15)
ms:contentKeyID: 48543493
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4eb46fa97b831030617916d03557b5bf9af9606d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291147"
---
# <a name="isolationlevel-property-ado"></a>IsolationLevel 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示 [Connection](connection-object-ado.md) 对象的隔离级别。

## <a name="settings-and-return-values"></a>设置和返回值

Sets or returns an [IsolationLevelEnum](isolationlevelenum.md) value. 默认值为“adXactChaos”****。

## <a name="remarks"></a>注解

使用 **IsolationLevel** 属性可设置 **Connection** 对象的隔离级别。直到下次调用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法时，该设置才会生效。如果请求的隔离级别不可用，则提供程序将返回下一个更高的隔离级别。

**IsolationLevel** 属性为可读写状态。

**远程数据服务使用情况**在客户端 Connection 对象上使用时, **IsolationLevel**属性只能设置为**adXactUnspecified**。

由于用户正在使用客户端缓存上的已断开连接的 **Recordset** 对象，因此可能会出现多用户问题。例如，两个不同的用户试图更新同一条记录时，远程数据服务只允许首先更新该记录的用户实现更新操作。另一个用户的更新请求将失败，并产生错误。

