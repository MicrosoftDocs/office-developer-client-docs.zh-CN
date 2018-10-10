---
title: WillMove 和 MoveComplete 事件 (ADO)
TOCTitle: WillMove and MoveComplete Events (ADO)
ms:assetid: fe7eb823-b388-6b3d-1ae9-056018032ef5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250307(v=office.15)
ms:contentKeyID: 48548937
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 875b9825b1482bbd33808cafc6df626b2e78b81b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466295"
---
# <a name="willmove-and-movecomplete-events-ado"></a><span data-ttu-id="d1df8-102">WillMove 和 MoveComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d1df8-102">WillMove and MoveComplete Events (ADO)</span></span>


<span data-ttu-id="d1df8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d1df8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d1df8-p101">在挂起操作更改 **Recordset** 中的当前位置之前调用 [WillMove](recordset-object-ado.md) 事件。在 **Recordset** 中的当前位置更改之后调用 **MoveComplete** 事件。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p101">The **WillMove** event is called before a pending operation changes the current position in the [Recordset](recordset-object-ado.md). The **MoveComplete** event is called after the current position in the **Recordset** changes.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1df8-106">语法</span><span class="sxs-lookup"><span data-stu-id="d1df8-106">Syntax</span></span>

<span data-ttu-id="d1df8-107">WillMove*adReason*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="d1df8-107">WillMove*adReason*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="d1df8-108">MoveComplete*adReason* *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="d1df8-108">MoveComplete*adReason*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="d1df8-109">参数</span><span class="sxs-lookup"><span data-stu-id="d1df8-109">Parameters</span></span>

  - <span data-ttu-id="d1df8-110">*adReason*</span><span class="sxs-lookup"><span data-stu-id="d1df8-110">*adReason*</span></span>

  - <span data-ttu-id="d1df8-p102">指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnMoveFirst** 、 **adRsnMoveLast** 、 **adRsnMoveNext** 、 **adRsnMovePrevious** 、 **adRsnMove** 或 **adRsnRequery** 。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p102">An [EventReasonEnum](eventreasonenum.md) value that specifies the reason for this event. Its value can be **adRsnMoveFirst**, **adRsnMoveLast**, **adRsnMoveNext**, **adRsnMovePrevious**, **adRsnMove**, or **adRsnRequery**.</span></span>

  - <span data-ttu-id="d1df8-113">*pError*</span><span class="sxs-lookup"><span data-stu-id="d1df8-113">*pError*</span></span>

  - <span data-ttu-id="d1df8-p103">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p103">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="d1df8-116">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="d1df8-116">*adStatus*</span></span>

  - [<span data-ttu-id="d1df8-117">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="d1df8-117">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="d1df8-p104">在调用 **WillMove** 时，如果引发事件的操作成功，则此参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p104">When **WillMove** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="d1df8-120">在调用 **MoveComplete** 时，如果引发事件的操作成功，则此参数设置为 **adStatusOK** ；如果操作失败则设置为 **adStatusErrorsOccurred** 。</span><span class="sxs-lookup"><span data-stu-id="d1df8-120">When **MoveComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span>
    
    <span data-ttu-id="d1df8-121">在 **WillMove** 返回之前，此参数设置为 **adStatusCancel** 以请求取消挂起操作，或设置为 adStatusUnwantedEvent 以禁止后续的通知。</span><span class="sxs-lookup"><span data-stu-id="d1df8-121">Before **WillMove** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation or set this parameter to adStatusUnwantedEvent to prevent subsequent notications.</span></span>
    
    <span data-ttu-id="d1df8-122">在 **MoveComplete** 返回之前，此参数设置为 **adStatusUnwantedEvent** 以禁止后续的通知。</span><span class="sxs-lookup"><span data-stu-id="d1df8-122">Before **MoveComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="d1df8-123">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="d1df8-123">*pRecordset*</span></span>

  - <span data-ttu-id="d1df8-p105">[Recordset](recordset-object-ado.md) 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p105">A [Recordset](recordset-object-ado.md) object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1df8-126">备注</span><span class="sxs-lookup"><span data-stu-id="d1df8-126">Remarks</span></span>

<span data-ttu-id="d1df8-p106">**WillMove** 或 **MoveComplete** 事件可能因以下 **Recordset** 操作而引发： [Open](open-method-ado-recordset.md)、[Move](move-method-ado.md)、[MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[AddNew](addnew-method-ado.md) 和 [Requery](requery-method-ado.md)。这两个事件可能由于以下属性而引发：[Filter](filter-property-ado.md)、[Index](index-property-ado.md)、[Bookmark](bookmark-property-ado.md)、[AbsolutePage](absolutepage-property-ado.md) 和 [AbsolutePosition](absoluteposition-property-ado.md)。如果子 **Recordset** 与 **Recordset** 事件相连且父 **Recordset** 被移动，那么也有可能发生这两个事件。</span><span class="sxs-lookup"><span data-stu-id="d1df8-p106">A **WillMove** or **MoveComplete** event may occur due to the following **Recordset** operations: [Open](open-method-ado-recordset.md), [Move](move-method-ado.md), [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [AddNew](addnew-method-ado.md), and [Requery](requery-method-ado.md). These events may occur because of the following properties: [Filter](filter-property-ado.md), [Index](index-property-ado.md), [Bookmark](bookmark-property-ado.md), [AbsolutePage](absolutepage-property-ado.md), and [AbsolutePosition](absoluteposition-property-ado.md). These events also occur if a child **Recordset** has **Recordset** events connected and the parent **Recordset** is moved.</span></span>

<span data-ttu-id="d1df8-130">对于每个可能的 adReason 值，必须将 **adStatus** 参数设置为 **adStatusUnwantedEvent** ，才能完全阻止包括 adReason 参数的任何事件的事件通知。</span><span class="sxs-lookup"><span data-stu-id="d1df8-130">You must set the **adStatus** parameter to **adStatusUnwantedEvent** for each possible adReason value in order to completely stop event notification for any event that includes an adReason parameter.</span></span>

