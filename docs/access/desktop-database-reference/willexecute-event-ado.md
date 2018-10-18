---
title: WillExecute 事件 (ADO)
TOCTitle: WillExecute Event (ADO)
ms:assetid: 9f516bfd-246d-9817-4ca3-64598ab466f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249732(v=office.15)
ms:contentKeyID: 48546686
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f3cdf4764cca2b40cee62f9d66ea748a4e627a5f
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606841"
---
# <a name="willexecute-event-ado"></a><span data-ttu-id="a179d-102">WillExecute 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a179d-102">WillExecute Event (ADO)</span></span>


<span data-ttu-id="a179d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a179d-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="a179d-104">**WillExecute** 事件在对连接执行挂起的命令之前的那一刻调用。</span><span class="sxs-lookup"><span data-stu-id="a179d-104">The **WillExecute** event is called just before a pending command executes on a connection.</span></span>

## <a name="syntax"></a><span data-ttu-id="a179d-105">语法</span><span class="sxs-lookup"><span data-stu-id="a179d-105">Syntax</span></span>

<span data-ttu-id="a179d-106">WillExecute*源*， *CursorType*， *LockType*、*选项*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="a179d-106">WillExecute*Source*, *CursorType*, *LockType*, *Options*, *adStatus*, *pCommand*, *pRecordset*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="a179d-107">参数</span><span class="sxs-lookup"><span data-stu-id="a179d-107">Parameters</span></span>

  - <span data-ttu-id="a179d-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="a179d-108">*Source*</span></span>

  - <span data-ttu-id="a179d-109">包含 SQL 命令或存储过程名称的 **字符串型** 。</span><span class="sxs-lookup"><span data-stu-id="a179d-109">A **String** that contains an SQL command or a stored procedure name.</span></span>

  - <span data-ttu-id="a179d-110">*CursorType*</span><span class="sxs-lookup"><span data-stu-id="a179d-110">*CursorType*</span></span>

  - <span data-ttu-id="a179d-111">包含将打开的 [Recordset](cursortypeenum.md) 的游标类型的 **CursorTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="a179d-111">A [CursorTypeEnum](cursortypeenum.md) that contains the type of cursor for the **Recordset** that will be opened.</span></span> <span data-ttu-id="a179d-112">使用此参数，您可以将光标更改为任何类型， **Recordset** [打开](open-method-ado-recordset.md)操作过程中。</span><span class="sxs-lookup"><span data-stu-id="a179d-112">With this parameter, you can change the cursor to any type during a **Recordset** [Open](open-method-ado-recordset.md) operation.</span></span> <span data-ttu-id="a179d-113">*CursorType*将被忽略任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="a179d-113">*CursorType* will be ignored for any other operation.</span></span>

  - <span data-ttu-id="a179d-114">*LockType*</span><span class="sxs-lookup"><span data-stu-id="a179d-114">*LockType*</span></span>

  - <span data-ttu-id="a179d-115">包含将打开的 [Recordset](locktypeenum.md) 的锁类型的 **LockTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="a179d-115">A [LockTypeEnum](locktypeenum.md) that contains the lock type for the **Recordset** that will be opened.</span></span> <span data-ttu-id="a179d-116">使用此参数可以在 **Recordset** 的 **Open** 操作期间将锁更改为其他类型。</span><span class="sxs-lookup"><span data-stu-id="a179d-116">With this parameter, you can change the lock to any type during a **Recordset** **Open** operation.</span></span> <span data-ttu-id="a179d-117">*LockType*将被忽略任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="a179d-117">*LockType* will be ignored for any other operation.</span></span>

  - <span data-ttu-id="a179d-118">*Options*</span><span class="sxs-lookup"><span data-stu-id="a179d-118">*Options*</span></span>

  - <span data-ttu-id="a179d-119">**长整型** 值，指示可用于执行命令或打开 **Recordset** 的选项。</span><span class="sxs-lookup"><span data-stu-id="a179d-119">A **Long** value that indicates options that can be used to execute the command or open the **Recordset**.</span></span>

  - <span data-ttu-id="a179d-120">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="a179d-120">*adStatus*</span></span>

  - [<span data-ttu-id="a179d-121">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="a179d-121">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="a179d-122">此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作。</span><span class="sxs-lookup"><span data-stu-id="a179d-122">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications, or **adStatusCancel** to request cancellation of the operation that caused this event.</span></span>

  - <span data-ttu-id="a179d-123">*pCommand*</span><span class="sxs-lookup"><span data-stu-id="a179d-123">*pCommand*</span></span>

  - <span data-ttu-id="a179d-124">为其应用该事件通知的 [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a179d-124">The [Command](command-object-ado.md) object for which this event notification applies.</span></span>

  - <span data-ttu-id="a179d-125">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="a179d-125">*pRecordset*</span></span>

  - <span data-ttu-id="a179d-126">为其应用该事件通知的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a179d-126">The [Recordset](recordset-object-ado.md) object for which this event notification applies.</span></span>

  - <span data-ttu-id="a179d-127">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="a179d-127">*pConnection*</span></span>

  - <span data-ttu-id="a179d-128">为其应用该事件通知的 [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="a179d-128">The [Connection](connection-object-ado.md) object for which this event notification applies.</span></span>

## <a name="remarks"></a><span data-ttu-id="a179d-129">备注</span><span class="sxs-lookup"><span data-stu-id="a179d-129">Remarks</span></span>

<span data-ttu-id="a179d-130"><<<<<<< 标头**WillExecute**事件可能出现 0:**连接。**[执行](https://msdn.microsoft.com/library/jj249832\(v=office.15\))**命令。**[执行](https://msdn.microsoft.com/library/jj248785\(v=office.15\))，或**Recordset。**[Open](open-method-ado-recordset.md)方法的*pConnection*参数应始终包含对**Connection**对象的有效引用。</span><span class="sxs-lookup"><span data-stu-id="a179d-130"><<<<<<< HEAD A **WillExecute** event may occur due to a **Connection.**[Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)), **Command.**[Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)), or **Recordset.**[Open](open-method-ado-recordset.md) method The *pConnection* parameter should always contain a valid reference to a **Connection** object.</span></span> <span data-ttu-id="a179d-131">如果由于**Connection.Execute**事件，在*pRecordset*和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-131">If the event is due to **Connection.Execute**, the *pRecordset* and *pCommand* parameters are set to **Nothing**.</span></span> <span data-ttu-id="a179d-132">如果由于**Recordset.Open**事件， *pRecordset*参数将引用的**Recordset**对象和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-132">If the event is due to **Recordset.Open**, the *pRecordset* parameter will reference the **Recordset** object and the *pCommand* parameter is set to **Nothing**.</span></span> <span data-ttu-id="a179d-133">如果由于**Command.Execute**事件， *pCommand*参数将引用的**Command**对象和*pRecordset*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-133">If the event is due to **Command.Execute**, the *pCommand* parameter will reference the **Command** object and the *pRecordset* parameter is set to **Nothing**.</span></span>
<span data-ttu-id="a179d-134">=== **WillExecute**事件可能会发生 0:**连接。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)**命令。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)，或**Recordset。**[Open](open-method-ado-recordset.md)方法的*pConnection*参数应始终包含对**Connection**对象的有效引用。</span><span class="sxs-lookup"><span data-stu-id="a179d-134">======= A **WillExecute** event may occur due to a **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection), **Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command), or **Recordset.**[Open](open-method-ado-recordset.md) method The *pConnection* parameter should always contain a valid reference to a **Connection** object.</span></span> <span data-ttu-id="a179d-135">如果由于**Connection.Execute**事件，在*pRecordset*和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-135">If the event is due to **Connection.Execute**, the *pRecordset* and *pCommand* parameters are set to **Nothing**.</span></span> <span data-ttu-id="a179d-136">如果由于**Recordset.Open**事件， *pRecordset*参数将引用的**Recordset**对象和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-136">If the event is due to **Recordset.Open**, the *pRecordset* parameter will reference the **Recordset** object and the *pCommand* parameter is set to **Nothing**.</span></span> <span data-ttu-id="a179d-137">如果由于**Command.Execute**事件， *pCommand*参数将引用的**Command**对象和*pRecordset*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="a179d-137">If the event is due to **Command.Execute**, the *pCommand* parameter will reference the **Command** object and the *pRecordset* parameter is set to **Nothing**.</span></span>
>>>>>>> <span data-ttu-id="a179d-138">master</span><span class="sxs-lookup"><span data-stu-id="a179d-138">master</span></span>

<span data-ttu-id="a179d-p104">**WillExecute** 允许您检查和修改挂起的执行的参数。该事件可以返回取消挂起的命令的请求。</span><span class="sxs-lookup"><span data-stu-id="a179d-p104">**WillExecute** allows you to examine and modify the pending execution parameters. This event may return a request that the pending command be canceled.</span></span>

