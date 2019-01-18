---
title: WillMove 和 MoveComplete 事件 (ADO)
TOCTitle: WillMove and MoveComplete events (ADO)
ms:assetid: fe7eb823-b388-6b3d-1ae9-056018032ef5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250307(v=office.15)
ms:contentKeyID: 48548937
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e663e18a13803097d490e0e315d139e6e15400da
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705958"
---
# <a name="willmove-and-movecomplete-events-ado"></a><span data-ttu-id="49c09-102">WillMove 和 MoveComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="49c09-102">WillMove and MoveComplete events (ADO)</span></span>

<span data-ttu-id="49c09-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="49c09-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="49c09-p101">在挂起操作更改 **Recordset** 中的当前位置之前调用 [WillMove](recordset-object-ado.md) 事件。在 **Recordset** 中的当前位置更改之后调用 **MoveComplete** 事件。</span><span class="sxs-lookup"><span data-stu-id="49c09-p101">The **WillMove** event is called before a pending operation changes the current position in the [Recordset](recordset-object-ado.md). The **MoveComplete** event is called after the current position in the **Recordset** changes.</span></span>

## <a name="syntax"></a><span data-ttu-id="49c09-106">语法</span><span class="sxs-lookup"><span data-stu-id="49c09-106">Syntax</span></span>

<span data-ttu-id="49c09-107">WillMove*adReason*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="49c09-107">WillMove*adReason*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="49c09-108">MoveComplete*adReason* *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="49c09-108">MoveComplete*adReason*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="49c09-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="49c09-109">Parameters</span></span>

|<span data-ttu-id="49c09-110">参数</span><span class="sxs-lookup"><span data-stu-id="49c09-110">Parameter</span></span>|<span data-ttu-id="49c09-111">说明</span><span class="sxs-lookup"><span data-stu-id="49c09-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="49c09-112">*adReason*</span><span class="sxs-lookup"><span data-stu-id="49c09-112">*adReason*</span></span> |<span data-ttu-id="49c09-p102">指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnMoveFirst** 、 **adRsnMoveLast** 、 **adRsnMoveNext** 、 **adRsnMovePrevious** 、 **adRsnMove** 或 **adRsnRequery** 。</span><span class="sxs-lookup"><span data-stu-id="49c09-p102">An [EventReasonEnum](eventreasonenum.md) value that specifies the reason for this event. Its value can be **adRsnMoveFirst**, **adRsnMoveLast**, **adRsnMoveNext**, **adRsnMovePrevious**, **adRsnMove**, or **adRsnRequery**.</span></span>|
|<span data-ttu-id="49c09-115">*pError*</span><span class="sxs-lookup"><span data-stu-id="49c09-115">*pError*</span></span> |<span data-ttu-id="49c09-p103">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="49c09-p103">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>|
|<span data-ttu-id="49c09-118">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="49c09-118">*adStatus*</span></span> |<span data-ttu-id="49c09-119">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="49c09-119">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="49c09-120">当调用**WillMove**时，此参数设置为**adStatusOK**如果导致事件的操作成功。</span><span class="sxs-lookup"><span data-stu-id="49c09-120">When **WillMove** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful.</span></span> <span data-ttu-id="49c09-121">如果此事件不能请求取消挂起的操作，它是设置为**adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="49c09-121">It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span> <br/><br/><span data-ttu-id="49c09-122">在调用 **MoveComplete** 时，如果引发事件的操作成功，则此参数设置为 **adStatusOK** ；如果操作失败则设置为 **adStatusErrorsOccurred** 。</span><span class="sxs-lookup"><span data-stu-id="49c09-122">When **MoveComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span> <br/><br/><span data-ttu-id="49c09-123">在 **WillMove** 返回之前，此参数设置为 **adStatusCancel** 以请求取消挂起操作，或设置为 adStatusUnwantedEvent 以禁止后续的通知。</span><span class="sxs-lookup"><span data-stu-id="49c09-123">Before **WillMove** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation or set this parameter to adStatusUnwantedEvent to prevent subsequent notications.</span></span> <br/><br/><span data-ttu-id="49c09-124">在 **MoveComplete** 返回之前，此参数设置为 **adStatusUnwantedEvent** 以禁止后续的通知。</span><span class="sxs-lookup"><span data-stu-id="49c09-124">Before **MoveComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>|
|<span data-ttu-id="49c09-125">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="49c09-125">*pRecordset*</span></span> |<span data-ttu-id="49c09-p105">[Recordset](recordset-object-ado.md) 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="49c09-p105">A [Recordset](recordset-object-ado.md) object. The **Recordset** for which this event occurred.</span></span>|

## <a name="remarks"></a><span data-ttu-id="49c09-128">备注</span><span class="sxs-lookup"><span data-stu-id="49c09-128">Remarks</span></span>

<span data-ttu-id="49c09-129">**WillMove**或**MoveComplete**事件可能由于以下**Recordset**操作发生：</span><span class="sxs-lookup"><span data-stu-id="49c09-129">A **WillMove** or **MoveComplete** event may occur due to the following **Recordset** operations:</span></span>

- [<span data-ttu-id="49c09-130">Open</span><span class="sxs-lookup"><span data-stu-id="49c09-130">Open</span></span>](open-method-ado-recordset.md)
- [<span data-ttu-id="49c09-131">Move</span><span class="sxs-lookup"><span data-stu-id="49c09-131">Move</span></span>](move-method-ado.md)
- [<span data-ttu-id="49c09-132">MoveFirst</span><span class="sxs-lookup"><span data-stu-id="49c09-132">MoveFirst</span></span>](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [<span data-ttu-id="49c09-133">MoveLast</span><span class="sxs-lookup"><span data-stu-id="49c09-133">MoveLast</span></span>](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [<span data-ttu-id="49c09-134">MoveNext</span><span class="sxs-lookup"><span data-stu-id="49c09-134">MoveNext</span></span>](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 
- [<span data-ttu-id="49c09-135">MovePrevious</span><span class="sxs-lookup"><span data-stu-id="49c09-135">MovePrevious</span></span>](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)
- [<span data-ttu-id="49c09-136">AddNew</span><span class="sxs-lookup"><span data-stu-id="49c09-136">AddNew</span></span>](addnew-method-ado.md)
- [<span data-ttu-id="49c09-137">Requery</span><span class="sxs-lookup"><span data-stu-id="49c09-137">Requery</span></span>](requery-method-ado.md)

<span data-ttu-id="49c09-138">由于以下属性可能会发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="49c09-138">These events may occur because of the following properties:</span></span>

- [<span data-ttu-id="49c09-139">Filter</span><span class="sxs-lookup"><span data-stu-id="49c09-139">Filter</span></span>](filter-property-ado.md)
- [<span data-ttu-id="49c09-140">索引</span><span class="sxs-lookup"><span data-stu-id="49c09-140">Index</span></span>](index-property-ado.md)
- [<span data-ttu-id="49c09-141">Bookmark</span><span class="sxs-lookup"><span data-stu-id="49c09-141">Bookmark</span></span>](bookmark-property-ado.md)
- [<span data-ttu-id="49c09-142">AbsolutePage</span><span class="sxs-lookup"><span data-stu-id="49c09-142">AbsolutePage</span></span>](absolutepage-property-ado.md)
- [<span data-ttu-id="49c09-143">AbsolutePosition</span><span class="sxs-lookup"><span data-stu-id="49c09-143">AbsolutePosition</span></span>](absoluteposition-property-ado.md)

<span data-ttu-id="49c09-144">如果子 **Recordset** 与 **Recordset** 事件相连且父 **Recordset** 被移动，那么也有可能发生这两个事件。</span><span class="sxs-lookup"><span data-stu-id="49c09-144">These events also occur if a child **Recordset** has **Recordset** events connected and the parent **Recordset** is moved.</span></span>

<span data-ttu-id="49c09-145">对于每个可能的 *adReason* 值，必须将 **adStatus** 参数设置为 *adStatusUnwantedEvent* ，才能完全阻止包括 *adReason* 参数的任何事件的事件通知。</span><span class="sxs-lookup"><span data-stu-id="49c09-145">You must set the *adStatus* parameter to **adStatusUnwantedEvent** for each possible *adReason* value in order to completely stop event notification for any event that includes an *adReason* parameter.</span></span>

