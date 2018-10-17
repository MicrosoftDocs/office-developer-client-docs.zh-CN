---
title: BeginTrans、CommitTrans 和 RollbackTrans 方法 (ADO)
TOCTitle: BeginTrans, CommitTrans, and RollbackTrans Methods (ADO)
ms:assetid: 9a0415f0-9424-8d1c-4779-92e932292d46
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249694(v=office.15)
ms:contentKeyID: 48546529
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 69d3d7830204ec400e01b64bb11434c272da5c29
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466775"
---
# <a name="begintrans-committrans-and-rollbacktrans-methods-ado"></a><span data-ttu-id="2cc6a-102">BeginTrans、CommitTrans 和 RollbackTrans 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2cc6a-102">BeginTrans, CommitTrans, and RollbackTrans Methods (ADO)</span></span>


<span data-ttu-id="2cc6a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2cc6a-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="2cc6a-104">以下事务方法用于管理 [Connection](connection-object-ado.md) 对象中的事务处理：</span><span class="sxs-lookup"><span data-stu-id="2cc6a-104">These transaction methods manage transaction processing within a [Connection](connection-object-ado.md) object as follows:</span></span>

  - <span data-ttu-id="2cc6a-105">**BeginTrans** - 开始新的事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-105">**BeginTrans** — Begins a new transaction.</span></span>

  - <span data-ttu-id="2cc6a-p101">**CommitTrans** - 保存任何更改并结束当前事务。还可以开始一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p101">**CommitTrans** — Saves any changes and ends the current transaction. It may also start a new transaction.</span></span>

  - <span data-ttu-id="2cc6a-p102">**RollbackTrans** - 取消当前事务过程中所做的任何更改并结束事务。还可以开始一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p102">**RollbackTrans** — Cancels any changes made during the current transaction and ends the transaction. It may also start a new transaction.</span></span>

## <a name="syntax"></a><span data-ttu-id="2cc6a-110">语法</span><span class="sxs-lookup"><span data-stu-id="2cc6a-110">Syntax</span></span>

<span data-ttu-id="2cc6a-111">*级别* = *对象*。BeginTrans()</span><span class="sxs-lookup"><span data-stu-id="2cc6a-111">*level* = *object*.BeginTrans()</span></span>

<span data-ttu-id="2cc6a-112">*对象*。BeginTrans</span><span class="sxs-lookup"><span data-stu-id="2cc6a-112">*object*.BeginTrans</span></span>

<span data-ttu-id="2cc6a-113">*对象*。CommitTrans</span><span class="sxs-lookup"><span data-stu-id="2cc6a-113">*object*.CommitTrans</span></span>

<span data-ttu-id="2cc6a-114">*对象*。RollbackTrans</span><span class="sxs-lookup"><span data-stu-id="2cc6a-114">*object*.RollbackTrans</span></span>

## <a name="return-value"></a><span data-ttu-id="2cc6a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2cc6a-115">Return Value</span></span>

<span data-ttu-id="2cc6a-116">**BeginTrans** 可以作为函数调用，返回一个 **长整型** 变量，用以指示事务的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-116">**BeginTrans** can be called as a function that returns a **Long** variable indicating the nesting level of the transaction.</span></span>

## <a name="parameters"></a><span data-ttu-id="2cc6a-117">参数</span><span class="sxs-lookup"><span data-stu-id="2cc6a-117">Parameters</span></span>

  - <span data-ttu-id="2cc6a-118">*object*</span><span class="sxs-lookup"><span data-stu-id="2cc6a-118">*object*</span></span>

  - <span data-ttu-id="2cc6a-119">**Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-119">A **Connection** object.</span></span>

<span data-ttu-id="2cc6a-120">**Connection**</span><span class="sxs-lookup"><span data-stu-id="2cc6a-120">**Connection**</span></span>

<span data-ttu-id="2cc6a-p103">如果要将对源数据所做的一系更改列作为一个整体进行保存或取消，那么可以对 **Connection** 对象使用这些方法。例如，若要在帐户之间转账，那么可以从一个帐户中减去该笔金额，并在另一个帐户中增加相同的金额。如果其中任意一个更新失败，那么这两个帐户之间将不再平衡。若在打开的事务中进行这些更改，即可确保所有更改全部生效或全都无效。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p103">Use these methods with a **Connection** object when you want to save or cancel a series of changes made to the source data as a single unit. For example, to transfer money between accounts, you subtract an amount from one and add the same amount to the other. If either update fails, the accounts no longer balance. Making these changes within an open transaction ensures that either all or none of the changes go through.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2cc6a-p104">并非所有的提供程序都支持事务。请确认提供程序定义的属性“<STRONG>Transaction DDL</STRONG>”出现在 <STRONG>Connection</STRONG> 对象的 <A href="properties-collection-ado.md">Properties</A> 集合中，这表示提供程序支持事务。如果提供程序不支持事务，则调用其中的任一方法将返回错误。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p104">Not all providers support transactions. Verify that the provider-defined property "<STRONG>Transaction DDL</STRONG>" appears in the <STRONG>Connection</STRONG> object's <A href="properties-collection-ado.md">Properties</A> collection, indicating that the provider supports transactions. If the provider does not support transactions, calling one of these methods will return an error.</span></span></P>



<span data-ttu-id="2cc6a-128">调用 **BeginTrans** 方法之后，提供程序将不再即时提交所做的更改，直至调用 **CommitTrans** 或 **RollbackTrans** 结束事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-128">After you call the **BeginTrans** method, the provider will no longer instantaneously commit changes you make until you call **CommitTrans** or **RollbackTrans** to end the transaction.</span></span>

<span data-ttu-id="2cc6a-p105">对于支持嵌套事务的提供程序，在打开的事务中调用 **BeginTrans** 方法将启动一个新的嵌套事务。返回值指示嵌套级别：返回值"1"指示打开一个顶级事务（即未嵌套在其他事务中的事务），"2"指示打开一个二级事务（嵌套在顶级事务中的事务），依此类推。调用 **CommitTrans** 或 **RollbackTrans** 只会影响最近打开的事务。必须先关闭或回滚当前事务，才能解决任何更高级别的事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p105">For providers that support nested transactions, calling the **BeginTrans** method within an open transaction starts a new, nested transaction. The return value indicates the level of nesting: a return value of "1" indicates you have opened a top-level transaction (that is, the transaction is not nested within another transaction), "2" indicates that you have opened a second-level transaction (a transaction nested within a top-level transaction), and so forth. Calling **CommitTrans** or **RollbackTrans** affects only the most recently opened transaction; you must close or roll back the current transaction before you can resolve any higher-level transactions.</span></span>

<span data-ttu-id="2cc6a-p106">调用 **CommitTrans** 方法将保存处于连接状态时在某个打开的事务中所做的更改，然后结束该事务；调用 **RollbackTrans** 方法将取消在某个打开的事务中所做的更改，然后结束该事务。如果不存在打开的事务，则调用任何一种方法都将产生错误。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p106">Calling the **CommitTrans** method saves changes made within an open transaction on the connection and ends the transaction. Calling the **RollbackTrans** method reverses any changes made within an open transaction and ends the transaction. Calling either method when there is no open transaction generates an error.</span></span>

<span data-ttu-id="2cc6a-p107">根据 **Connection** 对象 [Attributes](attributes-property-ado.md) 属性的不同，调用 **CommitTrans** 或 **RollbackTrans** 方法可能会自动启动一个新的事务。如果 **Attributes** 属性设置为 **adXactCommitRetaining** ，那么提供程序会在 **CommitTrans** 调用之后自动启动一个新的事务。如果 **Attributes** 属性设置为 **adXactAbortRetaining** ，那么提供程序会在 **RollbackTrans** 调用之后自动启动一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-p107">Depending on the **Connection** object's [Attributes](attributes-property-ado.md) property, calling either the **CommitTrans** or **RollbackTrans** methods may automatically start a new transaction. If the **Attributes** property is set to **adXactCommitRetaining**, the provider automatically starts a new transaction after a **CommitTrans** call. If the **Attributes** property is set to **adXactAbortRetaining**, the provider automatically starts a new transaction after a **RollbackTrans** call.</span></span>

<span data-ttu-id="2cc6a-138">**远程数据服务**</span><span class="sxs-lookup"><span data-stu-id="2cc6a-138">**Remote Data Service**</span></span>

<span data-ttu-id="2cc6a-139">对于客户端 **Connection** 对象， **BeginTrans** 、 **CommitTrans** 和 **RollbackTrans** 方法不可用。</span><span class="sxs-lookup"><span data-stu-id="2cc6a-139">The **BeginTrans**, **CommitTrans**, and **RollbackTrans** methods are not available on a client-side **Connection** object.</span></span>
