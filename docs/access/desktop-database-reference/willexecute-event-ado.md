---
title: WillExecute 事件 (ADO)
TOCTitle: WillExecute event (ADO)
ms:assetid: 9f516bfd-246d-9817-4ca3-64598ab466f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249732(v=office.15)
ms:contentKeyID: 48546686
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7fe15604d0160afcbde5fdf02eaa6a7831da874b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718565"
---
# <a name="willexecute-event-ado"></a><span data-ttu-id="e2f45-102">WillExecute 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e2f45-102">WillExecute event (ADO)</span></span>

<span data-ttu-id="e2f45-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e2f45-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e2f45-104">**WillExecute** 事件在对连接执行挂起的命令之前的那一刻调用。</span><span class="sxs-lookup"><span data-stu-id="e2f45-104">The **WillExecute** event is called just before a pending command executes on a connection.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2f45-105">语法</span><span class="sxs-lookup"><span data-stu-id="e2f45-105">Syntax</span></span>

<span data-ttu-id="e2f45-106">WillExecute*源*， *CursorType*， *LockType*、*选项*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="e2f45-106">WillExecute*Source*, *CursorType*, *LockType*, *Options*, *adStatus*, *pCommand*, *pRecordset*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="e2f45-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="e2f45-107">Parameters</span></span>

|<span data-ttu-id="e2f45-108">参数</span><span class="sxs-lookup"><span data-stu-id="e2f45-108">Parameter</span></span>|<span data-ttu-id="e2f45-109">说明</span><span class="sxs-lookup"><span data-stu-id="e2f45-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="e2f45-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="e2f45-110">*Source*</span></span> |<span data-ttu-id="e2f45-111">包含 SQL 命令或存储过程名称的 **字符串型** 。</span><span class="sxs-lookup"><span data-stu-id="e2f45-111">A **String** that contains an SQL command or a stored procedure name.</span></span>|
|<span data-ttu-id="e2f45-112">*CursorType*</span><span class="sxs-lookup"><span data-stu-id="e2f45-112">*CursorType*</span></span> |<span data-ttu-id="e2f45-113">包含将打开的 [Recordset](cursortypeenum.md) 的游标类型的 **CursorTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="e2f45-113">A [CursorTypeEnum](cursortypeenum.md) that contains the type of cursor for the **Recordset** that will be opened.</span></span> <span data-ttu-id="e2f45-114">使用此参数，您可以将光标更改为任何类型， **Recordset** [打开](open-method-ado-recordset.md)操作过程中。</span><span class="sxs-lookup"><span data-stu-id="e2f45-114">With this parameter, you can change the cursor to any type during a **Recordset** [Open](open-method-ado-recordset.md) operation.</span></span> <span data-ttu-id="e2f45-115">*CursorType*将被忽略任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="e2f45-115">*CursorType* will be ignored for any other operation.</span></span>|
|<span data-ttu-id="e2f45-116">*LockType*</span><span class="sxs-lookup"><span data-stu-id="e2f45-116">*LockType*</span></span> |<span data-ttu-id="e2f45-117">包含将打开的 [Recordset](locktypeenum.md) 的锁类型的 **LockTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="e2f45-117">A [LockTypeEnum](locktypeenum.md) that contains the lock type for the **Recordset** that will be opened.</span></span> <span data-ttu-id="e2f45-118">使用此参数可以在 **Recordset** 的 **Open** 操作期间将锁更改为其他类型。</span><span class="sxs-lookup"><span data-stu-id="e2f45-118">With this parameter, you can change the lock to any type during a **Recordset** **Open** operation.</span></span> <span data-ttu-id="e2f45-119">*LockType*将被忽略任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="e2f45-119">*LockType* will be ignored for any other operation.</span></span>|
|<span data-ttu-id="e2f45-120">*Options*</span><span class="sxs-lookup"><span data-stu-id="e2f45-120">*Options*</span></span> |<span data-ttu-id="e2f45-121">**长整型** 值，指示可用于执行命令或打开 **Recordset** 的选项。</span><span class="sxs-lookup"><span data-stu-id="e2f45-121">A **Long** value that indicates options that can be used to execute the command or open the **Recordset**.</span></span>|
|<span data-ttu-id="e2f45-122">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="e2f45-122">*adStatus*</span></span> |<span data-ttu-id="e2f45-123">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="e2f45-123">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="e2f45-124">此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作。</span><span class="sxs-lookup"><span data-stu-id="e2f45-124">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications, or **adStatusCancel** to request cancellation of the operation that caused this event.</span></span>|
|<span data-ttu-id="e2f45-125">*pCommand*</span><span class="sxs-lookup"><span data-stu-id="e2f45-125">*pCommand*</span></span> |<span data-ttu-id="e2f45-126">为其应用该事件通知的 [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="e2f45-126">The [Command](command-object-ado.md) object for which this event notification applies.</span></span>|
|<span data-ttu-id="e2f45-127">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="e2f45-127">*pRecordset*</span></span> |<span data-ttu-id="e2f45-128">为其应用该事件通知的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="e2f45-128">The [Recordset](recordset-object-ado.md) object for which this event notification applies.</span></span>|
|<span data-ttu-id="e2f45-129">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="e2f45-129">*pConnection*</span></span> |<span data-ttu-id="e2f45-130">为其应用该事件通知的 [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="e2f45-130">The [Connection](connection-object-ado.md) object for which this event notification applies.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e2f45-131">备注</span><span class="sxs-lookup"><span data-stu-id="e2f45-131">Remarks</span></span>

<span data-ttu-id="e2f45-132">**WillExecute**事件可能出现 0:**连接。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)**命令。**[执行](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)，或**Recordset。**[Open](open-method-ado-recordset.md)方法的*pConnection*参数应始终包含对**Connection**对象的有效引用。</span><span class="sxs-lookup"><span data-stu-id="e2f45-132">A **WillExecute** event may occur due to a **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection), **Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command), or **Recordset.**[Open](open-method-ado-recordset.md) method The *pConnection* parameter should always contain a valid reference to a **Connection** object.</span></span> <span data-ttu-id="e2f45-133">如果由于**Connection.Execute**事件，在*pRecordset*和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="e2f45-133">If the event is due to **Connection.Execute**, the *pRecordset* and *pCommand* parameters are set to **Nothing**.</span></span> <span data-ttu-id="e2f45-134">如果由于**Recordset.Open**事件， *pRecordset*参数将引用的**Recordset**对象和*pCommand*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="e2f45-134">If the event is due to **Recordset.Open**, the *pRecordset* parameter will reference the **Recordset** object and the *pCommand* parameter is set to **Nothing**.</span></span> <span data-ttu-id="e2f45-135">如果由于**Command.Execute**事件， *pCommand*参数将引用的**Command**对象和*pRecordset*参数设置为**Nothing**。</span><span class="sxs-lookup"><span data-stu-id="e2f45-135">If the event is due to **Command.Execute**, the *pCommand* parameter will reference the **Command** object and the *pRecordset* parameter is set to **Nothing**.</span></span>

<span data-ttu-id="e2f45-p105">**WillExecute** 允许您检查和修改挂起的执行的参数。该事件可以返回取消挂起的命令的请求。</span><span class="sxs-lookup"><span data-stu-id="e2f45-p105">**WillExecute** allows you to examine and modify the pending execution parameters. This event may return a request that the pending command be canceled.</span></span>

