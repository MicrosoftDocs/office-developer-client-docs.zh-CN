---
title: WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)
TOCTitle: WillChangeRecordset and RecordsetChangeComplete Events (ADO)
ms:assetid: 2cec4cf9-a4e9-c386-5202-04e86f4cf8ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249068(v=office.15)
ms:contentKeyID: 48543963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0a7bf9a69fd5a648efc86f698e82ca0ba9413a30
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886310"
---
# <a name="willchangerecordset-and-recordsetchangecomplete-events-ado"></a><span data-ttu-id="86ddd-102">WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="86ddd-102">WillChangeRecordset and RecordsetChangeComplete Events (ADO)</span></span>


<span data-ttu-id="86ddd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="86ddd-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="86ddd-p101">**WillChangeRecordset** 事件在挂起的操作更改 [Recordset](recordset-object-ado.md) 之前调用。 **RecordsetChangeComplete** 事件在 **Recordset** 已更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p101">The **WillChangeRecordset** event is called before a pending operation changes the [Recordset](recordset-object-ado.md). The **RecordsetChangeComplete** event is called after the **Recordset** has changed.</span></span>

## <a name="syntax"></a><span data-ttu-id="86ddd-106">语法</span><span class="sxs-lookup"><span data-stu-id="86ddd-106">Syntax</span></span>

<span data-ttu-id="86ddd-107">在 WillChangeRecordset*adReason*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="86ddd-107">WillChangeRecordset*adReason*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="86ddd-108">RecordsetChangeComplete*adReason* *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="86ddd-108">RecordsetChangeComplete*adReason*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="86ddd-109">参数</span><span class="sxs-lookup"><span data-stu-id="86ddd-109">Parameters</span></span>

  - <span data-ttu-id="86ddd-110">*adReason*</span><span class="sxs-lookup"><span data-stu-id="86ddd-110">*adReason*</span></span>

  - <span data-ttu-id="86ddd-p102">指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnRequery** 、 **adRsnResynch** 、 **adRsnClose** 和 **adRsnOpen** 。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p102">An [EventReasonEnum](eventreasonenum.md) value that specifies the reason for this event. Its value can be **adRsnRequery**, **adRsnResynch**, **adRsnClose**, **adRsnOpen**.</span></span>

  - <span data-ttu-id="86ddd-113">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="86ddd-113">*adStatus*</span></span>

  - [<span data-ttu-id="86ddd-114">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="86ddd-114">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="86ddd-p103">调用 **WillChangeRecordset** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p103">When **WillChangeRecordset** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="86ddd-117">调用 **RecordsetChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果操作失败，则该参数设置为 **adStatusErrorsOccurred** ；如果与以前接受的 **WillChangeRecordset** 事件关联的操作已被取消，则该参数设置为 **adStatusCancel** 。</span><span class="sxs-lookup"><span data-stu-id="86ddd-117">When **RecordsetChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, **adStatusErrorsOccurred** if the operation failed, or **adStatusCancel** if the operation associated with the previously accepted **WillChangeRecordset** event has been canceled.</span></span>
    
    <span data-ttu-id="86ddd-118">在 **WillChangeRecordset** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作，将该参数设置为 adStatusUnwantedEvent 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="86ddd-118">Before **WillChangeRecordset** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation or set this parameter to adStatusUnwantedEvent to prevent subsequent notifications.</span></span>
    
    <span data-ttu-id="86ddd-119">在 **WillChangeRecordset** 或 **RecordsetChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="86ddd-119">Before **WillChangeRecordset** or **RecordsetChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="86ddd-120">*pError*</span><span class="sxs-lookup"><span data-stu-id="86ddd-120">*pError*</span></span>

  - <span data-ttu-id="86ddd-p104">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p104">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="86ddd-123">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="86ddd-123">*pRecordset*</span></span>

  - <span data-ttu-id="86ddd-p105">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p105">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="86ddd-126">备注</span><span class="sxs-lookup"><span data-stu-id="86ddd-126">Remarks</span></span>

<span data-ttu-id="86ddd-127">**WillChangeRecordset**或**RecordsetChangeComplete**事件可能发生的**Recordset**的[Requery](requery-method-ado.md)或[Open](open-method-ado-recordset.md)方法。</span><span class="sxs-lookup"><span data-stu-id="86ddd-127">A **WillChangeRecordset** or **RecordsetChangeComplete** event may occur due to the **Recordset** [Requery](requery-method-ado.md) or [Open](open-method-ado-recordset.md) methods.</span></span>

<span data-ttu-id="86ddd-p106">如果提供程序不支持书签，则每次从提供程序检索新行时，会发生 **RecordsetChange** 事件通知。该事件的频率取决于 **RecordsetCacheSize** 属性。</span><span class="sxs-lookup"><span data-stu-id="86ddd-p106">If the provider does not support bookmarks, a **RecordsetChange** event notification occurs each time new rows are retrieved from the provider. The frequency of this event depends on the **RecordsetCacheSize** property.</span></span>

<span data-ttu-id="86ddd-130">对于每个可能的 **adReason** 值，必须将 **adStatus** 参数设置为 **adStatusUnwantedEvent** ，才能完全阻止包括 **adReason** 参数的任何事件的事件通知。</span><span class="sxs-lookup"><span data-stu-id="86ddd-130">You must set the **adStatus** parameter to **adStatusUnwantedEvent** for each possible **adReason** value in order to completely stop event notification for any event that includes an **adReason** parameter.</span></span>

