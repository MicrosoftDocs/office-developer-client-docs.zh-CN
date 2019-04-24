---
title: WillChangeField 和 FieldChangeComplete 事件 (ADO)
TOCTitle: WillChangeField and FieldChangeComplete events (ADO)
ms:assetid: bc4455a6-2925-33dc-d04f-8ea570e5e370
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249904(v=office.15)
ms:contentKeyID: 48547407
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0fd952cc09f410752f3eb7b5963059f8d6ee7c2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302483"
---
# <a name="willchangefield-and-fieldchangecomplete-events-ado"></a><span data-ttu-id="f073a-102">WillChangeField 和 FieldChangeComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f073a-102">WillChangeField and FieldChangeComplete events (ADO)</span></span>

<span data-ttu-id="f073a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f073a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f073a-p101">**WillChangeField** 事件在挂起的操作更改 [Recordset](recordset-object-ado.md) 中的一个或多个 [Field](field-object-ado.md) 对象的值之前调用。**FieldChangeComplete** 事件在一个或多个 **Field** 对象的值已更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="f073a-p101">The **WillChangeField** event is called before a pending operation changes the value of one or more [Field](field-object-ado.md) objects in the [Recordset](recordset-object-ado.md). The **FieldChangeComplete** event is called after the value of one or more **Field** objects has changed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f073a-106">语法</span><span class="sxs-lookup"><span data-stu-id="f073a-106">Syntax</span></span>

<span data-ttu-id="f073a-107">WillChangeField*cFields*、 *Fields*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="f073a-107">WillChangeField*cFields*, *Fields*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="f073a-108">FieldChangeComplete*cFields*、 *Fields*、 *pError*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="f073a-108">FieldChangeComplete*cFields*, *Fields*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="f073a-109">参数</span><span class="sxs-lookup"><span data-stu-id="f073a-109">Parameters</span></span>

|<span data-ttu-id="f073a-110">参数</span><span class="sxs-lookup"><span data-stu-id="f073a-110">Parameter</span></span>|<span data-ttu-id="f073a-111">描述</span><span class="sxs-lookup"><span data-stu-id="f073a-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="f073a-112">*cFields*</span><span class="sxs-lookup"><span data-stu-id="f073a-112">*cFields*</span></span> |<span data-ttu-id="f073a-113">**长整型**值，指示 *Fields* 中 **Field** 对象的数量。</span><span class="sxs-lookup"><span data-stu-id="f073a-113">A **Long** that indicates the number of **Field** objects in *Fields*.</span></span>|
|<span data-ttu-id="f073a-114">*Fields*</span><span class="sxs-lookup"><span data-stu-id="f073a-114">*Fields*</span></span> |<span data-ttu-id="f073a-115">对于 **WillChangeField**，*Fields* 参数是包含具有原始值的 **Field** 对象的**变量型**数组。</span><span class="sxs-lookup"><span data-stu-id="f073a-115">For **WillChangeField**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the original values.</span></span> <br/><br/><span data-ttu-id="f073a-116">
对于 \*\*FieldChangeComplete\**，\*Fields\* 参数是包含值发生更改的 \*\*Field*\* 对象的\*\*变量型\*\*数组。</span><span class="sxs-lookup"><span data-stu-id="f073a-116">For **FieldChangeComplete**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the changed values.</span></span>|
|<span data-ttu-id="f073a-117">*pError*</span><span class="sxs-lookup"><span data-stu-id="f073a-117">*pError*</span></span> |<span data-ttu-id="f073a-p102">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="f073a-p102">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>|
|<span data-ttu-id="f073a-120">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="f073a-120">*adStatus*</span></span> |<span data-ttu-id="f073a-121">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="f073a-121">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="f073a-122">当调用**WillChangeField**时, 如果导致事件的操作成功, 则将此参数设置为**adstatusok;** 。</span><span class="sxs-lookup"><span data-stu-id="f073a-122">When **WillChangeField** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful.</span></span> <span data-ttu-id="f073a-123">如果此事件无法请求取消挂起的操作, 则将其设置为**adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="f073a-123">It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span> <br/><br/><span data-ttu-id="f073a-124">调用 **FieldChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。</span><span class="sxs-lookup"><span data-stu-id="f073a-124">When **FieldChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span> <br/><br/><span data-ttu-id="f073a-125">在 **WillChangeField** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="f073a-125">Before **WillChangeField** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation.</span></span> <br/><br/><span data-ttu-id="f073a-126">在 **FieldChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="f073a-126">Before **FieldChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>|
|<span data-ttu-id="f073a-127">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="f073a-127">*pRecordset*</span></span> |<span data-ttu-id="f073a-p104">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="f073a-p104">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f073a-130">注解</span><span class="sxs-lookup"><span data-stu-id="f073a-130">Remarks</span></span>

<span data-ttu-id="f073a-131">设置 [Value](value-property-ado.md) 属性并调用带有字段和值数组参数的 [Update](update-method-ado.md) 方法时，可能会发生 **WillChangeField** 或 **FieldChangeComplete** 事件。</span><span class="sxs-lookup"><span data-stu-id="f073a-131">A **WillChangeField** or **FieldChangeComplete** event may occur when setting the [Value](value-property-ado.md) property and calling the [Update](update-method-ado.md) method with field and value array parameters.</span></span>

