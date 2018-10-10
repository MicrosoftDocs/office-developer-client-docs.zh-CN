---
title: 事务处理
TOCTitle: Transaction Processing
ms:assetid: 7cacf3bb-e523-8739-f9ff-c8663c9ddfeb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249523(v=office.15)
ms:contentKeyID: 48545842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a598b2842638b0c58e72ef2b802c8214f5c72b8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466762"
---
# <a name="transaction-processing"></a>事务处理


**适用于**： Access 2013 |Office 2013

ADO 提供下列用于控制事务的方法： **BeginTrans** 、 **CommitTrans** 和 **RollbackTrans** 。当您希望将对源数据进行的一系列更改作为一个整体来保存或取消时，可以将这些方法用于 **Connection** 对象。例如，若要在帐户之间转帐，可以从一个帐户中减去一定的金额并在另一个帐户中增加相同的金额。如果任一更新失败，则帐户将不再平衡。在开放式事务中进行这些更改可确保所有的更改都完成或者都未完成。


> [!NOTE]
> <P>并非所有的提供程序都支持事务。请确认提供程序定义的属性“<STRONG>Transaction DDL</STRONG>”出现在 <STRONG>Connection</STRONG> 对象的 <A href="properties-collection-ado.md">Properties</A> 集合中，这表示提供程序支持事务。如果提供程序不支持事务，则调用其中的任一方法将返回错误。</P>



调用 **BeginTrans** 方法之后，提供程序将不再即时提交所做的更改，直至调用 **CommitTrans** 或 **RollbackTrans** 结束事务。

调用 **CommitTrans** 方法将保存处于连接状态时在某个打开的事务中所做的更改，然后结束该事务；调用 **RollbackTrans** 方法将取消在某个打开的事务中所做的更改，然后结束该事务。如果不存在打开的事务，则调用任何一种方法都将产生错误。

根据 **Connection** 对象的 [Attributes](attributes-property-ado.md) 属性，调用 **CommitTrans** 或 **RollbackTrans** 方法可能会自动启动新事务。如果 **Attributes** 属性设置为 **adXactCommitRetaining** ，提供程序会自动在 **CommitTrans** 调用之后启动新事务。如果 **Attributes** 属性设置为 **adXactAbortRetaining** ，提供程序会自动在 **RollbackTrans** 调用之后启动新事务。

## <a name="transaction-isolation-level"></a>事务隔离级别

使用 **IsolationLevel** 属性可以设置 **Connection** 对象上事务的隔离级别。直到下次调用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法时，该设置才会生效。如果您请求的隔离级别不可用，提供程序可能会返回下一个较高的隔离级别。有关有效值的更多详细信息，请参阅《ADO 程序员参考》中的 **IsolationLevel** 属性。

## <a name="nested-transactions"></a>嵌套事务

对于支持嵌套事务的提供程序，在打开的事务中调用 **BeginTrans** 方法将启动一个新的嵌套事务。返回值指示嵌套级别：返回值"1"指示打开一个顶级事务（即未嵌套在其他事务中的事务），"2"指示打开一个二级事务（嵌套在顶级事务中的事务），依此类推。调用 **CommitTrans** 或 **RollbackTrans** 只会影响最近打开的事务。必须先关闭或回滚当前事务，才能解决任何更高级别的事务。

