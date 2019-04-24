---
title: BeginTransComplete、CommitTransComplete、RollbackTransComplete 事件 (ADO)
TOCTitle: BeginTransComplete, CommitTransComplete, and RollbackTransComplete events (ADO)
ms:assetid: 9d0ae38e-530a-7a89-a344-f3ab401c2e35
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249713(v=office.15)
ms:contentKeyID: 48546615
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a6f86e17a44ec0813176a023a02710fded627488
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296820"
---
# <a name="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado"></a><span data-ttu-id="a092c-102">BeginTransComplete、CommitTransComplete 和 RollbackTransComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a092c-102">BeginTransComplete, CommitTransComplete, and RollbackTransComplete events (ADO)</span></span>

<span data-ttu-id="a092c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a092c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a092c-104">这些事件将在对 [Connection](connection-object-ado.md) 对象的关联操作执行完毕之后调用。</span><span class="sxs-lookup"><span data-stu-id="a092c-104">These events will be called after the associated operation on the [Connection](connection-object-ado.md) object finishes executing.</span></span>

- <span data-ttu-id="a092c-105">**BeginTransComplete** 在 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="a092c-105">**BeginTransComplete** is called after the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) operation.</span></span>

- <span data-ttu-id="a092c-106">**CommitTransComplete** 在 [CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="a092c-106">**CommitTransComplete** is called after the [CommitTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) operation.</span></span>

- <span data-ttu-id="a092c-107">**RollbackTransComplete** 在 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="a092c-107">**RollbackTransComplete** is called after the [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) operation.</span></span>

## <a name="syntax"></a><span data-ttu-id="a092c-108">语法</span><span class="sxs-lookup"><span data-stu-id="a092c-108">Syntax</span></span>

<span data-ttu-id="a092c-109">BeginTransComplete*TransactionLevel*、 *pError*、 *adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="a092c-109">BeginTransComplete*TransactionLevel*, *pError*, *adStatus*, *pConnection*</span></span>

<span data-ttu-id="a092c-110">CommitTransComplete*pError*、 *adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="a092c-110">CommitTransComplete*pError*, *adStatus*, *pConnection*</span></span>

<span data-ttu-id="a092c-111">RollbackTransComplete*pError*、 *adStatus*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="a092c-111">RollbackTransComplete*pError*, *adStatus*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="a092c-112">参数</span><span class="sxs-lookup"><span data-stu-id="a092c-112">Parameters</span></span>

|<span data-ttu-id="a092c-113">参数</span><span class="sxs-lookup"><span data-stu-id="a092c-113">Parameter</span></span>|<span data-ttu-id="a092c-114">描述</span><span class="sxs-lookup"><span data-stu-id="a092c-114">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="a092c-115">*TransactionLevel*</span><span class="sxs-lookup"><span data-stu-id="a092c-115">*TransactionLevel*</span></span> |<span data-ttu-id="a092c-116">**长整型** 值，包含导致该事件的新事务级别的 **BeginTrans** 。</span><span class="sxs-lookup"><span data-stu-id="a092c-116">A **Long** value that contains the new transaction level of the **BeginTrans** that caused this event.</span></span>|
|<span data-ttu-id="a092c-117">*pError*</span><span class="sxs-lookup"><span data-stu-id="a092c-117">*pError*</span></span> |<span data-ttu-id="a092c-118">[Error](error-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a092c-118">An [Error](error-object-ado.md) object.</span></span> <span data-ttu-id="a092c-119">它描述了 EventStatusEnum 的值为**adStatusErrorsOccurred**时所发生的错误;否则, 它将不会设置。</span><span class="sxs-lookup"><span data-stu-id="a092c-119">It describes the error that occurred if the value of EventStatusEnum is **adStatusErrorsOccurred**; otherwise, it is not set.</span></span>|
|<span data-ttu-id="a092c-120">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="a092c-120">*adStatus*</span></span> |<span data-ttu-id="a092c-121">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="a092c-121">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="a092c-122">通过在事件返回之前将该参数设置为 **adStatusUnwantedEvent** ，这些事件可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="a092c-122">These events can prevent subsequent notifications by setting this parameter to **adStatusUnwantedEvent** before the event returns.</span></span>|
|<span data-ttu-id="a092c-123">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="a092c-123">*pConnection*</span></span> |<span data-ttu-id="a092c-124">发生此事件的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="a092c-124">The **Connection** object for which this event occurred.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a092c-125">注解</span><span class="sxs-lookup"><span data-stu-id="a092c-125">Remarks</span></span>

<span data-ttu-id="a092c-p103">在 Visual C++ 中，多个 **Connection** 可以共享相同的事件处理方法。方法使用返回的 **Connection** 对象来确定导致事件发生的对象。</span><span class="sxs-lookup"><span data-stu-id="a092c-p103">In Visual C++, multiple **Connections** can share the same event handling method. The method uses the returned **Connection** object to determine which object caused the event.</span></span>

<span data-ttu-id="a092c-p104">如果 [Attributes](attributes-property-ado.md) 属性设置为 **adXactCommitRetaining** 或 **adXactAbortRetaining** ，则在提交或回滚事务之后，将开始新的事务。使用 **BeginTransComplete** 事件将忽略除第一个事务开始事件以外的所有事件。</span><span class="sxs-lookup"><span data-stu-id="a092c-p104">If the [Attributes](attributes-property-ado.md) property is set to **adXactCommitRetaining** or **adXactAbortRetaining**, a new transaction starts after committing or rolling back a transaction. Use the **BeginTransComplete** event to ignore all but the first transaction start event.</span></span>

