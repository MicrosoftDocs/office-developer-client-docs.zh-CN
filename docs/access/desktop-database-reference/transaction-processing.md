---
title: 事务处理
TOCTitle: Transaction Processing
ms:assetid: 7cacf3bb-e523-8739-f9ff-c8663c9ddfeb
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249523(v=office.15)
ms:contentKeyID: 48545842
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 24e7940c86b079d5eb51fa894426a19e7700bf39
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937482"
---
# <a name="transaction-processing"></a><span data-ttu-id="c4207-102">事务处理</span><span class="sxs-lookup"><span data-stu-id="c4207-102">Transaction Processing</span></span>


<span data-ttu-id="c4207-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4207-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c4207-p101">ADO 提供下列用于控制事务的方法： **BeginTrans** 、 **CommitTrans** 和 **RollbackTrans** 。当您希望将对源数据进行的一系列更改作为一个整体来保存或取消时，可以将这些方法用于 **Connection** 对象。例如，若要在帐户之间转帐，可以从一个帐户中减去一定的金额并在另一个帐户中增加相同的金额。如果任一更新失败，则帐户将不再平衡。在开放式事务中进行这些更改可确保所有的更改都完成或者都未完成。</span><span class="sxs-lookup"><span data-stu-id="c4207-p101">ADO provides the following methods for controlling transactions: **BeginTrans**, **CommitTrans**, and **RollbackTrans**. Use these methods with a **Connection** object when you want to save or cancel a series of changes made to the source data as a single unit. For example, to transfer money between accounts, you subtract an amount from one and add the same amount to the other. If either update fails, the accounts no longer balance. Making these changes within an open transaction ensures that either all or none of the changes go through.</span></span>


> [!NOTE]
> <P><span data-ttu-id="c4207-p102">并非所有的提供程序都支持事务。请确认提供程序定义的属性“<STRONG>Transaction DDL</STRONG>”出现在 <STRONG>Connection</STRONG> 对象的 <A href="properties-collection-ado.md">Properties</A> 集合中，这表示提供程序支持事务。如果提供程序不支持事务，则调用其中的任一方法将返回错误。</span><span class="sxs-lookup"><span data-stu-id="c4207-p102">Not all providers support transactions. Verify that the provider-defined property "<STRONG>Transaction DDL</STRONG>" appears in the <STRONG>Connection</STRONG> object's <A href="properties-collection-ado.md">Properties</A> collection, indicating that the provider supports transactions. If the provider does not support transactions, calling one of these methods will return an error.</span></span></P>



<span data-ttu-id="c4207-112">调用 **BeginTrans** 方法之后，提供程序将不再即时提交所做的更改，直至调用 **CommitTrans** 或 **RollbackTrans** 结束事务。</span><span class="sxs-lookup"><span data-stu-id="c4207-112">After you call the **BeginTrans** method, the provider will no longer instantaneously commit changes you make until you call **CommitTrans** or **RollbackTrans** to end the transaction.</span></span>

<span data-ttu-id="c4207-p103">调用 **CommitTrans** 方法将保存处于连接状态时在某个打开的事务中所做的更改，然后结束该事务；调用 **RollbackTrans** 方法将取消在某个打开的事务中所做的更改，然后结束该事务。如果不存在打开的事务，则调用任何一种方法都将产生错误。</span><span class="sxs-lookup"><span data-stu-id="c4207-p103">Calling the **CommitTrans** method saves changes made within an open transaction on the connection and ends the transaction. Calling the **RollbackTrans** method reverses any changes made within an open transaction and ends the transaction. Calling either method when there is no open transaction generates an error.</span></span>

<span data-ttu-id="c4207-p104">根据 **Connection** 对象的 [Attributes](attributes-property-ado.md) 属性，调用 **CommitTrans** 或 **RollbackTrans** 方法可能会自动启动新事务。如果 **Attributes** 属性设置为 **adXactCommitRetaining** ，提供程序会自动在 **CommitTrans** 调用之后启动新事务。如果 **Attributes** 属性设置为 **adXactAbortRetaining** ，提供程序会自动在 **RollbackTrans** 调用之后启动新事务。</span><span class="sxs-lookup"><span data-stu-id="c4207-p104">Depending on the **Connection** object's [Attributes](attributes-property-ado.md) property, calling either the **CommitTrans** or **RollbackTrans** method may automatically start a new transaction. If the **Attributes** property is set to **adXactCommitRetaining**, the provider automatically starts a new transaction after a **CommitTrans** call. If the **Attributes** property is set to **adXactAbortRetaining**, the provider automatically starts a new transaction after a **RollbackTrans** call.</span></span>

## <a name="transaction-isolation-level"></a><span data-ttu-id="c4207-119">事务隔离级别</span><span class="sxs-lookup"><span data-stu-id="c4207-119">Transaction Isolation Level</span></span>

<span data-ttu-id="c4207-120">使用 **IsolationLevel** 属性可以设置 **Connection** 对象上事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="c4207-120">Use the **IsolationLevel** property to set the isolation level of a transaction on a **Connection** object.</span></span> <span data-ttu-id="c4207-121">直到下次调用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法时，该设置才会生效。</span><span class="sxs-lookup"><span data-stu-id="c4207-121">The setting does not take effect until the next time you call the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method.</span></span> <span data-ttu-id="c4207-122">如果您请求的隔离级别不可用，提供程序可能会返回下一个较高的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="c4207-122">If the level of isolation you request is unavailable, the provider may return the next greater level of isolation.</span></span> <span data-ttu-id="c4207-123">请参阅 ADO 程序员参考 （英文） 上有效的值的更多详细信息中的**IsolationLevel**属性。</span><span class="sxs-lookup"><span data-stu-id="c4207-123">Refer to the **IsolationLevel** property in the ADO programmer's reference for more details on valid values.</span></span>

## <a name="nested-transactions"></a><span data-ttu-id="c4207-124">嵌套事务</span><span class="sxs-lookup"><span data-stu-id="c4207-124">Nested Transactions</span></span>

<span data-ttu-id="c4207-p106">对于支持嵌套事务的提供程序，在打开的事务中调用 **BeginTrans** 方法将启动一个新的嵌套事务。返回值指示嵌套级别：返回值"1"指示打开一个顶级事务（即未嵌套在其他事务中的事务），"2"指示打开一个二级事务（嵌套在顶级事务中的事务），依此类推。调用 **CommitTrans** 或 **RollbackTrans** 只会影响最近打开的事务。必须先关闭或回滚当前事务，才能解决任何更高级别的事务。</span><span class="sxs-lookup"><span data-stu-id="c4207-p106">For providers that support nested transactions, calling the **BeginTrans** method within an open transaction starts a new, nested transaction. The return value indicates the level of nesting: a return value of "1" indicates you have opened a top-level transaction (that is, the transaction is not nested within another transaction), "2" indicates that you have opened a second-level transaction (a transaction nested within a top-level transaction), and so forth. Calling **CommitTrans** or **RollbackTrans** affects only the most recently opened transaction; you must close or roll back the current transaction before you can resolve any higher-level transactions.</span></span>

