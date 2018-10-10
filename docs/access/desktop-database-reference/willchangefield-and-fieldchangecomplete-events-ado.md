---
title: WillChangeField 和 FieldChangeComplete 事件 (ADO)
TOCTitle: WillChangeField and FieldChangeComplete Events (ADO)
ms:assetid: bc4455a6-2925-33dc-d04f-8ea570e5e370
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249904(v=office.15)
ms:contentKeyID: 48547407
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 40e9572988ca3335ef93ecf46d00a716ba29c595
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467715"
---
# <a name="willchangefield-and-fieldchangecomplete-events-ado"></a><span data-ttu-id="191ba-102">WillChangeField 和 FieldChangeComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="191ba-102">WillChangeField and FieldChangeComplete Events (ADO)</span></span>


<span data-ttu-id="191ba-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="191ba-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="191ba-p101">**WillChangeField** 事件在挂起的操作更改 [Recordset](field-object-ado.md) 中的一个或多个 [Field](recordset-object-ado.md) 对象的值之前调用。 **FieldChangeComplete** 事件在一个或多个 **Field** 对象的值已更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="191ba-p101">The **WillChangeField** event is called before a pending operation changes the value of one or more [Field](field-object-ado.md) objects in the [Recordset](recordset-object-ado.md). The **FieldChangeComplete** event is called after the value of one or more **Field** objects has changed.</span></span>

## <a name="syntax"></a><span data-ttu-id="191ba-106">语法</span><span class="sxs-lookup"><span data-stu-id="191ba-106">Syntax</span></span>

<span data-ttu-id="191ba-107">WillChangeField*cFields*，*字段*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="191ba-107">WillChangeField*cFields*, *Fields*, *adStatus*, *pRecordset*</span></span>

<span data-ttu-id="191ba-108">FieldChangeComplete*cFields*，*字段*， *pError* *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="191ba-108">FieldChangeComplete*cFields*, *Fields*, *pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="191ba-109">参数</span><span class="sxs-lookup"><span data-stu-id="191ba-109">Parameters</span></span>

  - <span data-ttu-id="191ba-110">*cFields*</span><span class="sxs-lookup"><span data-stu-id="191ba-110">*cFields*</span></span>

  - <span data-ttu-id="191ba-111">**长整型**值，指示 *Fields* 中 **Field** 对象的数量。</span><span class="sxs-lookup"><span data-stu-id="191ba-111">A **Long** that indicates the number of **Field** objects in *Fields*.</span></span>

  - <span data-ttu-id="191ba-112">*Fields*</span><span class="sxs-lookup"><span data-stu-id="191ba-112">*Fields*</span></span>

  - <span data-ttu-id="191ba-113">对于**WillChangeField**，*字段*参数是包含的原始值与**Field**对象的**变量**的数组。</span><span class="sxs-lookup"><span data-stu-id="191ba-113">For **WillChangeField**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the original values.</span></span>  
      
    <span data-ttu-id="191ba-114">对于**FieldChangeComplete**，*字段*参数是包含更改的值与**Field**对象的**变量**的数组。</span><span class="sxs-lookup"><span data-stu-id="191ba-114">For **FieldChangeComplete**, the *Fields* parameter is an array of **Variants** that contains **Field** objects with the changed values.</span></span>

  - <span data-ttu-id="191ba-115">*pError*</span><span class="sxs-lookup"><span data-stu-id="191ba-115">*pError*</span></span>

  - <span data-ttu-id="191ba-p102">[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="191ba-p102">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of *adStatus* is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="191ba-118">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="191ba-118">*adStatus*</span></span>

  - [<span data-ttu-id="191ba-119">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="191ba-119">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="191ba-p103">调用 **WillChangeField** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="191ba-p103">When **WillChangeField** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="191ba-122">调用 **FieldChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。</span><span class="sxs-lookup"><span data-stu-id="191ba-122">When **FieldChangeComplete** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful, or to **adStatusErrorsOccurred** if the operation failed.</span></span>
    
    <span data-ttu-id="191ba-123">在 **WillChangeField** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="191ba-123">Before **WillChangeField** returns, set this parameter to **adStatusCancel** to request cancellation of the pending operation.</span></span>
    
    <span data-ttu-id="191ba-124">在 **FieldChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="191ba-124">Before **FieldChangeComplete** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="191ba-125">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="191ba-125">*pRecordset*</span></span>

  - <span data-ttu-id="191ba-p104">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="191ba-p104">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="191ba-128">备注</span><span class="sxs-lookup"><span data-stu-id="191ba-128">Remarks</span></span>

<span data-ttu-id="191ba-129">设置 **Value** 属性并调用带有字段和值数组参数的 **Update** 方法时，可能会发生 [WillChangeField](value-property-ado.md) 或 [FieldChangeComplete](update-method-ado.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="191ba-129">A **WillChangeField** or **FieldChangeComplete** event may occur when setting the [Value](value-property-ado.md) property and calling the [Update](update-method-ado.md) method with field and value array parameters.</span></span>

