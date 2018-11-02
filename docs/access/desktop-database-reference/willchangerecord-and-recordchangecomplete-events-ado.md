---
title: WillChangeRecord 和 RecordChangeComplete 事件 (ADO)
TOCTitle: WillChangeRecord and RecordChangeComplete events (ADO)
ms:assetid: b21229b2-74e6-0798-95bf-0252f041831c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249851(v=office.15)
ms:contentKeyID: 48547162
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3177e27d3485d8a4ec6adafaa03d968fc15fa62a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925955"
---
# <a name="willchangerecord-and-recordchangecomplete-events-ado"></a><span data-ttu-id="88e1b-102">WillChangeRecord 和 RecordChangeComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="88e1b-102">WillChangeRecord and RecordChangeComplete events (ADO)</span></span>


<span data-ttu-id="88e1b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="88e1b-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="88e1b-p101">**WillChangeRecord** 事件在 [Recordset](recordset-object-ado.md) 中的一个或多个记录（行）发生更改之前调用。 **RecordChangeComplete** 事件在一个或多个记录发生更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="88e1b-p101">The **WillChangeRecord** event is called before one or more records (rows) in the [Recordset](recordset-object-ado.md) change. The **RecordChangeComplete** event is called after one or more records change.</span></span>

## <a name="syntax"></a><span data-ttu-id="88e1b-106">语法</span><span class="sxs-lookup"><span data-stu-id="88e1b-106">Syntax</span></span>

<span data-ttu-id="88e1b-107">WillChangeRecord*adReason* *cRecords*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="88e1b-107">WillChangeRecord*adReason*, *cRecords*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="88e1b-108">RecordChangeComplete*adReason*、 *cRecords*、 *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="88e1b-108">RecordChangeComplete*adReason*, *cRecords*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="88e1b-109">参数</span><span class="sxs-lookup"><span data-stu-id="88e1b-109">Parameters</span></span>

  - <span data-ttu-id="88e1b-110">*adReason*</span><span class="sxs-lookup"><span data-stu-id="88e1b-110">*adReason*</span></span>

  - <span data-ttu-id="88e1b-p102">指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnAddNew** 、 **adRsnDelete** 、 **adRsnUpdate** 、 **adRsnUndoUpdate** 、 **adRsnUndoAddNew** 、 **adRsnUndoDelete** 或 **adRsnFirstChange** 。</span><span class="sxs-lookup"><span data-stu-id="88e1b-p102">An [EventReasonEnum](eventreasonenum.md) value that specifies the reason for this event. Its value can be **adRsnAddNew**, **adRsnDelete**, **adRsnUpdate**, **adRsnUndoUpdate**, **adRsnUndoAddNew**, **adRsnUndoDelete**, or **adRsnFirstChange**.</span></span>

  - <span data-ttu-id="88e1b-113">*cRecords*</span><span class="sxs-lookup"><span data-stu-id="88e1b-113">*cRecords*</span></span>

  - <span data-ttu-id="88e1b-114">**长整型** 值，指定记录更改（受影响）的数量。</span><span class="sxs-lookup"><span data-stu-id="88e1b-114">A **Long** value that indicates the number of records changing (affected).</span></span>

  - <span data-ttu-id="88e1b-115">*pError*</span><span class="sxs-lookup"><span data-stu-id="88e1b-115">*pError*</span></span>

  - <span data-ttu-id="88e1b-p103">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="88e1b-p103">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="88e1b-118">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="88e1b-118">*adStatus*</span></span>

  - [<span data-ttu-id="88e1b-119">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="88e1b-119">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="88e1b-p104">调用 **WillChangeRecord** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="88e1b-p104">When **WillChangeRecord** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="88e1b-122">调用 **RecordChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。</span><span class="sxs-lookup"><span data-stu-id="88e1b-122">When **RecordChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span>
    
    <span data-ttu-id="88e1b-123">在 **WillChangeRecord** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消导致该事件的操作，将该参数设置为 adStatusUnwantedEvent 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="88e1b-123">Before **WillChangeRecord** returns, set this parameter to **adStatusCancel** to request cancellation of the operation that caused this event or set this parameter to adStatusUnwantedEvent to prevent subsequent notications.</span></span>
    
    <span data-ttu-id="88e1b-124">在 **RecordChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="88e1b-124">Before **RecordChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="88e1b-125">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="88e1b-125">*pRecordset*</span></span>

  - <span data-ttu-id="88e1b-p105">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="88e1b-p105">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="88e1b-128">备注</span><span class="sxs-lookup"><span data-stu-id="88e1b-128">Remarks</span></span>

<span data-ttu-id="88e1b-129">由于以下 **Recordset** 操作，行中第一个发生更改的字段可能会导致发生 **WillChangeRecord** 或 **RecordChangeComplete** 事件： [Update](update-method-ado.md)、[Delete](delete-method-ado-recordset.md)、[CancelUpdate](cancelupdate-method-ado.md)、[AddNew](addnew-method-ado.md)、[UpdateBatch](updatebatch-method-ado.md) 和 [CancelBatch](cancelbatch-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="88e1b-129">A **WillChangeRecord** or **RecordChangeComplete** event may occur for the first changed field in a row due to the following **Recordset** operations: [Update](update-method-ado.md), [Delete](delete-method-ado-recordset.md), [CancelUpdate](cancelupdate-method-ado.md), [AddNew](addnew-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), and [CancelBatch](cancelbatch-method-ado.md).</span></span> <span data-ttu-id="88e1b-130">**Recordset** [CursorType](cursortype-property-ado.md)的值确定哪个操作导致事件发生。</span><span class="sxs-lookup"><span data-stu-id="88e1b-130">The value of the **Recordset** [CursorType](cursortype-property-ado.md) determines which operations cause the events to occur.</span></span>

<span data-ttu-id="88e1b-131">**WillChangeRecord**事件期间， **Recordset** [Filter](filter-property-ado.md)属性设置为**adFilterAffectedRecords**。</span><span class="sxs-lookup"><span data-stu-id="88e1b-131">During the **WillChangeRecord** event, the **Recordset** [Filter](filter-property-ado.md) property is set to **adFilterAffectedRecords**.</span></span> <span data-ttu-id="88e1b-132">在处理事件的时候不能更改此属性。</span><span class="sxs-lookup"><span data-stu-id="88e1b-132">You cannot change this property while processing the event.</span></span>

<span data-ttu-id="88e1b-133">对于每个可能的 adReason 值，必须将 adStatus 参数设置为 adStatusUnwantedEvent，以完全停止包含 adReason 参数的任何事件的事件通知。</span><span class="sxs-lookup"><span data-stu-id="88e1b-133">You must set the adStatus parameter to adStatusUnwantedEvent for each possible adReason value in order to completely stop event noticiation for any event that includes an adReason parameter.</span></span>

