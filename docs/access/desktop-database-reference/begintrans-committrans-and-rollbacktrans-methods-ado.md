---
title: BeginTrans、CommitTrans 和 RollbackTrans 方法 (ADO)
TOCTitle: BeginTrans, CommitTrans, and RollbackTrans methods (ADO)
ms:assetid: 9a0415f0-9424-8d1c-4779-92e932292d46
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249694(v=office.15)
ms:contentKeyID: 48546529
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ca7c63e0c310535ecdf84a11c656d00ff436627f
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945920"
---
# <a name="begintrans-committrans-and-rollbacktrans-methods-ado"></a>BeginTrans、CommitTrans 和 RollbackTrans 方法 (ADO)

**适用于**： Access 2013、 Office 2013

以下事务方法用于管理 [Connection](connection-object-ado.md) 对象中的事务处理：

- **BeginTrans** - 开始新的事务。

- **CommitTrans** - 保存任何更改并结束当前事务。还可以开始一个新的事务。

- **RollbackTrans** - 取消当前事务过程中所做的任何更改并结束事务。还可以开始一个新的事务。

## <a name="syntax"></a>语法

*级别* = *对象*。BeginTrans()

*对象*。BeginTrans

*对象*。CommitTrans

*对象*。RollbackTrans

## <a name="return-value"></a>返回值

**BeginTrans** 可以作为函数调用，返回一个 **长整型** 变量，用以指示事务的嵌套级别。

## <a name="parameters"></a>参数

- *object*

  - **Connection** 对象。

### <a name="connection"></a>Connection

如果要将对源数据所做的一系更改列作为一个整体进行保存或取消，那么可以对 **Connection** 对象使用这些方法。例如，若要在帐户之间转账，那么可以从一个帐户中减去该笔金额，并在另一个帐户中增加相同的金额。如果其中任意一个更新失败，那么这两个帐户之间将不再平衡。若在打开的事务中进行这些更改，即可确保所有更改全部生效或全都无效。

> [!NOTE]
> 并非所有的提供程序都支持事务。请确认提供程序定义的属性“**Transaction DDL**”出现在 **Connection** 对象的 [Properties](properties-collection-ado.md) 集合中，这表示提供程序支持事务。如果提供程序不支持事务，则调用其中的任一方法将返回错误。

调用 **BeginTrans** 方法之后，提供程序将不再即时提交所做的更改，直至调用 **CommitTrans** 或 **RollbackTrans** 结束事务。

对于支持嵌套事务的提供程序，在打开的事务中调用 **BeginTrans** 方法将启动一个新的嵌套事务。返回值指示嵌套级别：返回值"1"指示打开一个顶级事务（即未嵌套在其他事务中的事务），"2"指示打开一个二级事务（嵌套在顶级事务中的事务），依此类推。调用 **CommitTrans** 或 **RollbackTrans** 只会影响最近打开的事务。必须先关闭或回滚当前事务，才能解决任何更高级别的事务。

调用 **CommitTrans** 方法将保存处于连接状态时在某个打开的事务中所做的更改，然后结束该事务；调用 **RollbackTrans** 方法将取消在某个打开的事务中所做的更改，然后结束该事务。如果不存在打开的事务，则调用任何一种方法都将产生错误。

根据 **Connection** 对象 [Attributes](attributes-property-ado.md) 属性的不同，调用 **CommitTrans** 或 **RollbackTrans** 方法可能会自动启动一个新的事务。如果 **Attributes** 属性设置为 **adXactCommitRetaining** ，那么提供程序会在 **CommitTrans** 调用之后自动启动一个新的事务。如果 **Attributes** 属性设置为 **adXactAbortRetaining** ，那么提供程序会在 **RollbackTrans** 调用之后自动启动一个新的事务。

### <a name="remote-data-service"></a>远程数据服务

对于客户端 **Connection** 对象， **BeginTrans** 、 **CommitTrans** 和 **RollbackTrans** 方法不可用。

