---
title: 什么是锁定？ （访问桌面数据库参考 （英文）
TOCTitle: What is a Lock?
ms:assetid: 9ddc3198-1531-1d8f-153d-fc79847e388a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249721(v=office.15)
ms:contentKeyID: 48546636
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 319e223afddfb0841c8bf292e01e07116e26477c
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946298"
---
# <a name="what-is-a-lock"></a>什么是锁定？


**适用于**： Access 2013、 Office 2013

锁定是一个进程，DBMS 在多用户环境中通过它来限制对行的访问。当某个用户以独占方式锁定行或列时，将不允许其他用户访问锁定数据，直到该锁定被解除。这可确保两个用户不能同时更新某一行中的同一列。

从资源的角度来看，锁定的成本会非常高，并且只应当在需要保持数据完整性时才使用。在数据库（如连接到 Internet 的数据库）中，每秒可能会有成千上万个用户尝试访问同一个记录，那么，不必要的锁定可能会迅速导致应用程序的执行速度降低。

可通过选择适当的锁定选项来控制数据源和 ADO 游标库管理并发的方式。

在打开 **Recordset** 前设置 **LockType** 属性可指定在打开该记录集时提供程序应使用的锁定类型。读取该属性将返回在打开的 **Recordset** 对象上使用的锁定类型。

提供程序可能不会支持所有的锁定类型。如果提供程序无法支持所请求的 **LockType** 设置，它将替换另一种类型的锁定。若要确定 **Recordset** 对象中实际可用的锁定功能，请将 [Supports](supports-method-ado.md) 方法与 **adUpdate** 和 **adUpdateBatch** 一起使用。

如果 **CursorLocation** 属性设置为 [adUseClient](cursorlocation-property-ado.md) ，则 **adLockPessimistic** 设置不受支持。如果所设置的值不受支持，并不产生错误；而是会使用最接近的受支持 **LockType** 。

当 **Recordset** 处于关闭状态时， **LockType** 属性是可读/写的，当记录集处于打开状态时，该属性是只读的。

本节包括下列主题：

- [锁定的类型](types-of-locks.md)

