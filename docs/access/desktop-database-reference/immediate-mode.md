---
title: 立即模式 （访问桌面数据库参考 （英文）
TOCTitle: Immediate mode
ms:assetid: 61bd3645-6e84-2e3a-7814-37d8c1247df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249362(v=office.15)
ms:contentKeyID: 48545220
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b6401e7954325eded85b70b9edb5d164e857d113
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947859"
---
# <a name="immediate-mode"></a>立即模式


**适用于**： Access 2013、 Office 2013

如果将 **LockType** 属性设置为 **adLockOptimistic** 或 **adLockPessimistic** ，则立即模式生效。在立即模式下，一旦通过调用 **Update** 方法声明对行的操作完成，则对记录的更改就会传播到数据源。

## <a name="calling-update"></a>调用 Update

如果在调用 **Update** 方法之前离开了正在添加或编辑的记录，ADO 将自动调用 **Update** 以保存更改。如果要取消对当前记录的任何更改或放弃新添加的记录，则必须在导航之前调用 **CancelUpdate** 方法。

调用 **Update** 方法之后，当前记录仍然是当前记录。

## <a name="cancelupdate"></a>CancelUpdate

使用 **CancelUpdate** 方法可以取消对当前行的任何更改或放弃新添加的行。在调用 **Update** 方法之后，不能取消对当前行或新行的更改，除非更改是可以用 **RollbackTrans** 方法回滚的事务的一部分，或者是批更新的一部分。在批更新情况下，可以用 **CancelUpdate** 或 **CancelBatch** 方法取消 **Update** 。

如果调用 **CancelUpdate** 方法时正在添加新行，则当前行将变成调用 **AddNew** 之前的当前行。

如果还没有更改当前行或添加新行，则调用 **CancelUpdate** 方法会生成错误。

