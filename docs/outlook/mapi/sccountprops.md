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
ms.openlocfilehash: 49634bda487143ddd8d8806b94f6c451ccf57b75
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351315"
---
# <a name="sccountprops"></a><span data-ttu-id="bc935-103">ScCountProps</span><span class="sxs-lookup"><span data-stu-id="bc935-103">ScCountProps</span></span>

  
  
<span data-ttu-id="bc935-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc935-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc935-105">确定属性值数组的大小 (以字节为单位), 并验证与该数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="bc935-105">Determines the size, in bytes, of a property value array and validates the memory associated with the array.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bc935-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="bc935-106">Header file:</span></span>  <br/> |<span data-ttu-id="bc935-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="bc935-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="bc935-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="bc935-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="bc935-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="bc935-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="bc935-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="bc935-110">Called by:</span></span>  <br/> |<span data-ttu-id="bc935-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="bc935-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCountProps(
  int cprop,
  LPSPropValue rgprop,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="bc935-112">参数</span><span class="sxs-lookup"><span data-stu-id="bc935-112">Parameters</span></span>

 <span data-ttu-id="bc935-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="bc935-113">_cprop_</span></span>
  
> <span data-ttu-id="bc935-114">实时由_rgprop_参数指示的数组中的属性计数。</span><span class="sxs-lookup"><span data-stu-id="bc935-114">[in] Count of properties in the array indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="bc935-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="bc935-115">_rgprop_</span></span>
  
> <span data-ttu-id="bc935-116">实时指向[SPropValue](spropvalue.md)结构数组中的区域的指针, 这些结构定义要确定其大小的属性。</span><span class="sxs-lookup"><span data-stu-id="bc935-116">[in] Pointer to a range in an array of [SPropValue](spropvalue.md) structures that defines the properties whose size is to be determined.</span></span> <span data-ttu-id="bc935-117">此范围不一定从数组的开头开始。</span><span class="sxs-lookup"><span data-stu-id="bc935-117">This range does not necessarily start at the beginning of the array.</span></span> 
    
 <span data-ttu-id="bc935-118">_pcb_</span><span class="sxs-lookup"><span data-stu-id="bc935-118">_pcb_</span></span>
  
> <span data-ttu-id="bc935-119">排除指向属性数组的大小 (以字节为单位) 的可选指针。</span><span class="sxs-lookup"><span data-stu-id="bc935-119">[out] Optional pointer to the size, in bytes, of the property array.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc935-120">返回值</span><span class="sxs-lookup"><span data-stu-id="bc935-120">Return value</span></span>

<span data-ttu-id="bc935-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc935-121">S_OK</span></span> 
  
> <span data-ttu-id="bc935-122">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="bc935-122">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="bc935-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="bc935-123">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="bc935-124">属性值数组中至少有一个属性的标识符为 PROP_ID_NULL 或 PROP_ID_INVALID, 或者属性数组包含无属性值的多值属性。</span><span class="sxs-lookup"><span data-stu-id="bc935-124">At least one property in the property value array has an identifier of PROP_ID_NULL or PROP_ID_INVALID, or the property array contains a multivalued property with no property values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bc935-125">注解</span><span class="sxs-lookup"><span data-stu-id="bc935-125">Remarks</span></span>

<span data-ttu-id="bc935-126">如果在_pcb_参数中传递 NULL, 则**ScCountProps**函数将验证通知数组, 但不执行任何计算。</span><span class="sxs-lookup"><span data-stu-id="bc935-126">If NULL is passed in the  _pcb_ parameter, the **ScCountProps** function validates the array of notifications but no counting is done.</span></span> <span data-ttu-id="bc935-127">如果在_pcb_中传递非 null 值, **ScCountNotifications**函数将确定数组的大小并存储原因_pcb_。</span><span class="sxs-lookup"><span data-stu-id="bc935-127">If a non-null value is passed in  _pcb_, the **ScCountNotifications** function determines the size of the array and stores the cause  _pcb_.</span></span> <span data-ttu-id="bc935-128">_pcb_参数的大小必须足以包含整个数组。</span><span class="sxs-lookup"><span data-stu-id="bc935-128">The  _pcb_ parameter must be large enough to contain the entire array.</span></span> 
  
<span data-ttu-id="bc935-129">在进行计数时, **ScCountProps**会验证与该数组关联的内存。</span><span class="sxs-lookup"><span data-stu-id="bc935-129">As it is counting, **ScCountProps** validates the memory associated with the array.</span></span> <span data-ttu-id="bc935-130">**ScCountProps**仅适用于有关 MAPI 包含其信息的属性。</span><span class="sxs-lookup"><span data-stu-id="bc935-130">**ScCountProps** only works with properties about which MAPI has information.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bc935-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc935-131">See also</span></span>



[<span data-ttu-id="bc935-132">PropCopyMore</span><span class="sxs-lookup"><span data-stu-id="bc935-132">PropCopyMore</span></span>](propcopymore.md)

