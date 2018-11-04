---
title: WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)
TOCTitle: WillChangeRecordset and RecordsetChangeComplete events (ADO)
ms:assetid: 2cec4cf9-a4e9-c386-5202-04e86f4cf8ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249068(v=office.15)
ms:contentKeyID: 48543963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 47d2c4a870151e8c917e7d00eca3e3d152bbfb8b
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950200"
---
# <a name="willchangerecordset-and-recordsetchangecomplete-events-ado"></a><span data-ttu-id="bec90-102">WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bec90-102">WillChangeRecordset and RecordsetChangeComplete events (ADO)</span></span>

<span data-ttu-id="bec90-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bec90-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bec90-p101">**WillChangeRecordset** 事件在挂起的操作更改 [Recordset](recordset-object-ado.md) 之前调用。 **RecordsetChangeComplete** 事件在 **Recordset** 已更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="bec90-p101">The **WillChangeRecordset** event is called before a pending operation changes the [Recordset](recordset-object-ado.md). The **RecordsetChangeComplete** event is called after the **Recordset** has changed.</span></span>

## <a name="syntax"></a><span data-ttu-id="bec90-106">语法</span><span class="sxs-lookup"><span data-stu-id="bec90-106">Syntax</span></span>

<span data-ttu-id="bec90-107">在 WillChangeRecordset*adReason*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="bec90-107">WillChangeRecordset*adReason*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="bec90-108">RecordsetChangeComplete*adReason* *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="bec90-108">RecordsetChangeComplete*adReason*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="bec90-109">参数</span><span class="sxs-lookup"><span data-stu-id="bec90-109">Parameters</span></span>

|<span data-ttu-id="bec90-110">参数</span><span class="sxs-lookup"><span data-stu-id="bec90-110">Parameter</span></span>|<span data-ttu-id="bec90-111">说明</span><span class="sxs-lookup"><span data-stu-id="bec90-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="bec90-112">*adReason*</span><span class="sxs-lookup"><span data-stu-id="bec90-112">*adReason*</span></span> |<span data-ttu-id="bec90-p102">指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnRequery** 、 **adRsnResynch** 、 **adRsnClose** 和 **adRsnOpen** 。</span><span class="sxs-lookup"><span data-stu-id="bec90-p102">An [EventReasonEnum](eventreasonenum.md) value that specifies the reason for this event. Its value can be **adRsnRequery**, **adRsnResynch**, **adRsnClose**, **adRsnOpen**.</span></span>|
|<span data-ttu-id="bec90-115">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="bec90-115">*adStatus*</span></span> |<span data-ttu-id="bec90-116">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="bec90-116">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="bec90-117">当调用**WillChangeRecordset**时，此参数设置为**adStatusOK**如果导致事件的操作成功。</span><span class="sxs-lookup"><span data-stu-id="bec90-117">When **WillChangeRecordset** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful.</span></span> <span data-ttu-id="bec90-118">如果此事件不能请求取消挂起的操作，它是设置为**adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="bec90-118">It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span> <br/><br/><span data-ttu-id="bec90-119">调用 **RecordsetChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果操作失败，则该参数设置为 **adStatusErrorsOccurred** ；如果与以前接受的 **WillChangeRecordset** 事件关联的操作已被取消，则该参数设置为 **adStatusCancel** 。</span><span class="sxs-lookup"><span data-stu-id="bec90-119">When **RecordsetChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, **adStatusErrorsOccurred** if the operation failed, or **adStatusCancel** if the operation associated with the previously accepted **WillChangeRecordset** event has been canceled.</span></span> <br/><br/><span data-ttu-id="bec90-120">在 **WillChangeRecordset** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作，将该参数设置为 adStatusUnwantedEvent 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="bec90-120">Before **WillChangeRecordset** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation or set this parameter to adStatusUnwantedEvent to prevent subsequent notifications.</span></span> <br/><br/><span data-ttu-id="bec90-121">在 **WillChangeRecordset** 或 **RecordsetChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="bec90-121">Before **WillChangeRecordset** or **RecordsetChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>|
|<span data-ttu-id="bec90-122">*pError*</span><span class="sxs-lookup"><span data-stu-id="bec90-122">*pError*</span></span> |<span data-ttu-id="bec90-p104">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="bec90-p104">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>|
|<span data-ttu-id="bec90-125">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="bec90-125">*pRecordset*</span></span> |<span data-ttu-id="bec90-p105">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="bec90-p105">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bec90-128">备注</span><span class="sxs-lookup"><span data-stu-id="bec90-128">Remarks</span></span>

<span data-ttu-id="bec90-129">**WillChangeRecordset**或**RecordsetChangeComplete**事件可能发生的**Recordset**的[Requery](requery-method-ado.md)或[Open](open-method-ado-recordset.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bec90-129">A **WillChangeRecordset** or **RecordsetChangeComplete** event may occur due to the **Recordset** [Requery](requery-method-ado.md) or [Open](open-method-ado-recordset.md) methods.</span></span>

<span data-ttu-id="bec90-p106">如果提供程序不支持书签，则每次从提供程序检索新行时，会发生 **RecordsetChange** 事件通知。该事件的频率取决于 **RecordsetCacheSize** 属性。</span><span class="sxs-lookup"><span data-stu-id="bec90-p106">If the provider does not support bookmarks, a **RecordsetChange** event notification occurs each time new rows are retrieved from the provider. The frequency of this event depends on the **RecordsetCacheSize** property.</span></span>

<span data-ttu-id="bec90-132">对于每个可能的 **adReason** 值，必须将 **adStatus** 参数设置为 **adStatusUnwantedEvent** ，才能完全阻止包括 **adReason** 参数的任何事件的事件通知。</span><span class="sxs-lookup"><span data-stu-id="bec90-132">You must set the **adStatus** parameter to **adStatusUnwantedEvent** for each possible **adReason** value in order to completely stop event notification for any event that includes an **adReason** parameter.</span></span>

