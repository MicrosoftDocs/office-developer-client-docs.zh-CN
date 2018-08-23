---
title: ScCountProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCountProps
api_type:
- COM
ms.assetid: 76e4cc52-e1a0-4e0b-a2a6-a17644f6b2e7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ee004bdfb8d13537fd8823225f155223ebc76ca7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583349"
---
# <a name="sccountprops"></a><span data-ttu-id="aa1f4-103">ScCountProps</span><span class="sxs-lookup"><span data-stu-id="aa1f4-103">ScCountProps</span></span>

  
  
<span data-ttu-id="aa1f4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa1f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa1f4-105">确定大小，以字节为单位，属性值数组，并验证与数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-105">Determines the size, in bytes, of a property value array and validates the memory associated with the array.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa1f4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="aa1f4-106">Header file:</span></span>  <br/> |<span data-ttu-id="aa1f4-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="aa1f4-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="aa1f4-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="aa1f4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="aa1f4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="aa1f4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="aa1f4-110">调用：</span><span class="sxs-lookup"><span data-stu-id="aa1f4-110">Called by:</span></span>  <br/> |<span data-ttu-id="aa1f4-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="aa1f4-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCountProps(
  int cprop,
  LPSPropValue rgprop,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="aa1f4-112">参数</span><span class="sxs-lookup"><span data-stu-id="aa1f4-112">Parameters</span></span>

 <span data-ttu-id="aa1f4-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="aa1f4-113">_cprop_</span></span>
  
> <span data-ttu-id="aa1f4-114">[in]由_rgprop_参数指示在阵列中的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-114">[in] Count of properties in the array indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="aa1f4-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="aa1f4-115">_rgprop_</span></span>
  
> <span data-ttu-id="aa1f4-116">[in]在范围定义的属性，其大小是确定[SPropValue](spropvalue.md)结构的数组中的指针。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-116">[in] Pointer to a range in an array of [SPropValue](spropvalue.md) structures that defines the properties whose size is to be determined.</span></span> <span data-ttu-id="aa1f4-117">此范围不一定是启动数组的开头。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-117">This range does not necessarily start at the beginning of the array.</span></span> 
    
 <span data-ttu-id="aa1f4-118">_pcb_</span><span class="sxs-lookup"><span data-stu-id="aa1f4-118">_pcb_</span></span>
  
> <span data-ttu-id="aa1f4-119">[输出]指向的大小，以字节为单位属性数组的可选指针。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-119">[out] Optional pointer to the size, in bytes, of the property array.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aa1f4-120">返回值</span><span class="sxs-lookup"><span data-stu-id="aa1f4-120">Return value</span></span>

<span data-ttu-id="aa1f4-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa1f4-121">S_OK</span></span> 
  
> <span data-ttu-id="aa1f4-122">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-122">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="aa1f4-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="aa1f4-123">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="aa1f4-124">属性值数组中的至少一个属性具有 PROP_ID_NULL 或 PROP_ID_INVALID，标识符或属性数组包含任何属性值的多值的属性。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-124">At least one property in the property value array has an identifier of PROP_ID_NULL or PROP_ID_INVALID, or the property array contains a multivalued property with no property values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aa1f4-125">注解</span><span class="sxs-lookup"><span data-stu-id="aa1f4-125">Remarks</span></span>

<span data-ttu-id="aa1f4-126">如果_pcb_参数中传递 NULL，则**ScCountProps**函数验证通知的数组，但没有计数完成。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-126">If NULL is passed in the  _pcb_ parameter, the **ScCountProps** function validates the array of notifications but no counting is done.</span></span> <span data-ttu-id="aa1f4-127">如果在_pcb_传递一个非空值，则**ScCountNotifications**函数确定数组的大小，并将存储原因_pcb_。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-127">If a non-null value is passed in  _pcb_, the **ScCountNotifications** function determines the size of the array and stores the cause  _pcb_.</span></span> <span data-ttu-id="aa1f4-128">_Pcb_参数必须为足够大，使其包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-128">The  _pcb_ parameter must be large enough to contain the entire array.</span></span> 
  
<span data-ttu-id="aa1f4-129">对其进行计数，如**ScCountProps**验证与数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-129">As it is counting, **ScCountProps** validates the memory associated with the array.</span></span> <span data-ttu-id="aa1f4-130">**ScCountProps**只适用于有关哪些 MAPI 包含信息的属性。</span><span class="sxs-lookup"><span data-stu-id="aa1f4-130">**ScCountProps** only works with properties about which MAPI has information.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="aa1f4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa1f4-131">See also</span></span>



[<span data-ttu-id="aa1f4-132">PropCopyMore</span><span class="sxs-lookup"><span data-stu-id="aa1f4-132">PropCopyMore</span></span>](propcopymore.md)

