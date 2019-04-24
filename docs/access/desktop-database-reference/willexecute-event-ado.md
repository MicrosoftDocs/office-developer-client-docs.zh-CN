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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302752"
---
# <a name="willexecute-event-ado"></a><span data-ttu-id="847a9-102">WillExecute 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="847a9-102">WillExecute event (ADO)</span></span>

<span data-ttu-id="847a9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="847a9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="847a9-104">**WillExecute** 事件在对连接执行挂起的命令之前的那一刻调用。</span><span class="sxs-lookup"><span data-stu-id="847a9-104">The **WillExecute** event is called just before a pending command executes on a connection.</span></span>

## <a name="syntax"></a><span data-ttu-id="847a9-105">语法</span><span class="sxs-lookup"><span data-stu-id="847a9-105">Syntax</span></span>

<span data-ttu-id="847a9-106">WillExecute*Source*、 *CursorType*、 *LockType*、 *Options*、 *adStatus*、 *pCommand*、 *pRecordset*、 *pConnection*</span><span class="sxs-lookup"><span data-stu-id="847a9-106">WillExecute*Source*, *CursorType*, *LockType*, *Options*, *adStatus*, *pCommand*, *pRecordset*, *pConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="847a9-107">参数</span><span class="sxs-lookup"><span data-stu-id="847a9-107">Parameters</span></span>

|<span data-ttu-id="847a9-108">参数</span><span class="sxs-lookup"><span data-stu-id="847a9-108">Parameter</span></span>|<span data-ttu-id="847a9-109">描述</span><span class="sxs-lookup"><span data-stu-id="847a9-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="847a9-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="847a9-110">*Source*</span></span> |<span data-ttu-id="847a9-111">包含 SQL 命令或存储过程名称的 **字符串型** 。</span><span class="sxs-lookup"><span data-stu-id="847a9-111">A **String** that contains an SQL command or a stored procedure name.</span></span>|
|<span data-ttu-id="847a9-112">*CursorType*</span><span class="sxs-lookup"><span data-stu-id="847a9-112">*CursorType*</span></span> |<span data-ttu-id="847a9-113">包含将打开的 [Recordset](cursortypeenum.md) 的游标类型的 **CursorTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="847a9-113">A [CursorTypeEnum](cursortypeenum.md) that contains the type of cursor for the **Recordset** that will be opened.</span></span> <span data-ttu-id="847a9-114">使用此参数, 可以在**Recordset** [打开](open-method-ado-recordset.md)操作过程中将光标更改为任何类型。</span><span class="sxs-lookup"><span data-stu-id="847a9-114">With this parameter, you can change the cursor to any type during a **Recordset** [Open](open-method-ado-recordset.md) operation.</span></span> <span data-ttu-id="847a9-115">对于任何其他操作，将忽略 *CursorType*。</span><span class="sxs-lookup"><span data-stu-id="847a9-115">*CursorType* will be ignored for any other operation.</span></span>|
|<span data-ttu-id="847a9-116">*LockType*</span><span class="sxs-lookup"><span data-stu-id="847a9-116">*LockType*</span></span> |<span data-ttu-id="847a9-117">包含将打开的 [Recordset](locktypeenum.md) 的锁类型的 **LockTypeEnum**。</span><span class="sxs-lookup"><span data-stu-id="847a9-117">A [LockTypeEnum](locktypeenum.md) that contains the lock type for the **Recordset** that will be opened.</span></span> <span data-ttu-id="847a9-118">使用此参数可以在 **Recordset** 的 **Open** 操作期间将锁更改为其他类型。</span><span class="sxs-lookup"><span data-stu-id="847a9-118">With this parameter, you can change the lock to any type during a **Recordset** **Open** operation.</span></span> <span data-ttu-id="847a9-119">对于任何其他操作，将忽略 *LockType*。</span><span class="sxs-lookup"><span data-stu-id="847a9-119">*LockType* will be ignored for any other operation.</span></span>|
|<span data-ttu-id="847a9-120">*Options*</span><span class="sxs-lookup"><span data-stu-id="847a9-120">*Options*</span></span> |<span data-ttu-id="847a9-121">**长整型** 值，指示可用于执行命令或打开 **Recordset** 的选项。</span><span class="sxs-lookup"><span data-stu-id="847a9-121">A **Long** value that indicates options that can be used to execute the command or open the **Recordset**.</span></span>|
|<span data-ttu-id="847a9-122">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="847a9-122">*adStatus*</span></span> |<span data-ttu-id="847a9-123">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="847a9-123">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="847a9-124">此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作。</span><span class="sxs-lookup"><span data-stu-id="847a9-124">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications, or **adStatusCancel** to request cancellation of the operation that caused this event.</span></span>|
|<span data-ttu-id="847a9-125">*pCommand*</span><span class="sxs-lookup"><span data-stu-id="847a9-125">*pCommand*</span></span> |<span data-ttu-id="847a9-126">为其应用该事件通知的 [Command](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="847a9-126">The [Command](command-object-ado.md) object for which this event notification applies.</span></span>|
|<span data-ttu-id="847a9-127">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="847a9-127">*pRecordset*</span></span> |<span data-ttu-id="847a9-128">为其应用该事件通知的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="847a9-128">The [Recordset](recordset-object-ado.md) object for which this event notification applies.</span></span>|
|<span data-ttu-id="847a9-129">*pConnection*</span><span class="sxs-lookup"><span data-stu-id="847a9-129">*pConnection*</span></span> |<span data-ttu-id="847a9-130">为其应用该事件通知的 [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="847a9-130">The [Connection](connection-object-ado.md) object for which this event notification applies.</span></span>|

## <a name="remarks"></a><span data-ttu-id="847a9-131">注解</span><span class="sxs-lookup"><span data-stu-id="847a9-131">Remarks</span></span>

<span data-ttu-id="847a9-p104">**WillExecute** 事件发生的原因可能是 **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection)、**Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 或 **Recordset.**[Open](open-method-ado-recordset.md) 方法。*pConnection* 参数始终包含对 **Connection** 对象的有效引用。如果事件发生的原因是 **Connection.Execute**，则 *pRecordset* 和 *pCommand* 参数设置为 **Nothing**。如果事件发生的原因是 **Recordset.Open**，则 *pRecordset* 参数将引用 **Recordset** 对象且 *pCommand* 参数设置为 **Nothing**。如果事件发生的原因是 **Command.Execute**，则 *pCommand* 参数将引用 **Command** 对象且 *pRecordset* 参数设置为 **Nothing**。</span><span class="sxs-lookup"><span data-stu-id="847a9-p104">A **WillExecute** event may occur due to a **Connection.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection), **Command.**[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command), or **Recordset.**[Open](open-method-ado-recordset.md) method The *pConnection* parameter should always contain a valid reference to a **Connection** object. If the event is due to **Connection.Execute**, the *pRecordset* and *pCommand* parameters are set to **Nothing**. If the event is due to **Recordset.Open**, the *pRecordset* parameter will reference the **Recordset** object and the *pCommand* parameter is set to **Nothing**. If the event is due to **Command.Execute**, the *pCommand* parameter will reference the **Command** object and the *pRecordset* parameter is set to **Nothing**.</span></span>

<span data-ttu-id="847a9-p105">**WillExecute** 允许您检查和修改挂起的执行的参数。该事件可以返回取消挂起的命令的请求。</span><span class="sxs-lookup"><span data-stu-id="847a9-p105">**WillExecute** allows you to examine and modify the pending execution parameters. This event may return a request that the pending command be canceled.</span></span>

