---
title: ScCopyProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCopyProps
api_type:
- COM
ms.assetid: 08bc256c-9706-4f3e-9a12-3e9cca5e4caa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1afd922459be2ec4bbbd27a61fdf6fcb425548c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411006"
---
# <a name="sccopyprops"></a><span data-ttu-id="f858c-103">ScCopyProps</span><span class="sxs-lookup"><span data-stu-id="f858c-103">ScCopyProps</span></span>

  
  
<span data-ttu-id="f858c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f858c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f858c-105">将由[SPropValue](spropvalue.md)结构数组定义的属性复制到新目标。</span><span class="sxs-lookup"><span data-stu-id="f858c-105">Copies the properties defined by an array of [SPropValue](spropvalue.md) structures to a new destination.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f858c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f858c-106">Header file:</span></span>  <br/> |<span data-ttu-id="f858c-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="f858c-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f858c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f858c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f858c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f858c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f858c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f858c-110">Called by:</span></span>  <br/> |<span data-ttu-id="f858c-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f858c-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCopyProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="f858c-112">参数</span><span class="sxs-lookup"><span data-stu-id="f858c-112">Parameters</span></span>

 <span data-ttu-id="f858c-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="f858c-113">_cprop_</span></span>
  
> <span data-ttu-id="f858c-114">实时要复制的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="f858c-114">[in] Count of properties to be copied.</span></span> 
    
 <span data-ttu-id="f858c-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="f858c-115">_rgprop_</span></span>
  
> <span data-ttu-id="f858c-116">实时指向定义要复制的属性的[SPropValue](spropvalue.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="f858c-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures that define the properties to be copied.</span></span> <span data-ttu-id="f858c-117">_rgprop_参数不必指向数组的开头, 但它必须指向数组中的一个**SPropValue**结构的开始位置。</span><span class="sxs-lookup"><span data-stu-id="f858c-117">The  _rgprop_ parameter does not have to point to the beginning of the array, but it must point to the beginning of one of the **SPropValue** structures in the array.</span></span> 
    
 <span data-ttu-id="f858c-118">_pvDst_</span><span class="sxs-lookup"><span data-stu-id="f858c-118">_pvDst_</span></span>
  
> <span data-ttu-id="f858c-119">实时指向此函数将在其中复制属性的内存中的初始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="f858c-119">[in] Pointer to the initial position in memory to which this function copies the properties.</span></span> 
    
 <span data-ttu-id="f858c-120">_pcb_</span><span class="sxs-lookup"><span data-stu-id="f858c-120">_pcb_</span></span>
  
> <span data-ttu-id="f858c-121">排除可选指针, 指向由_pvDst_参数指向的内存块的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="f858c-121">[out] Optional pointer to the size, in bytes, of the block of memory pointed to by the  _pvDst_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f858c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="f858c-122">Return value</span></span>

<span data-ttu-id="f858c-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="f858c-123">S_OK</span></span>
  
> <span data-ttu-id="f858c-124">已成功复制属性。</span><span class="sxs-lookup"><span data-stu-id="f858c-124">Properties were copied successfully.</span></span>
    
<span data-ttu-id="f858c-125">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f858c-125">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="f858c-126">遇到未知的属性类型。</span><span class="sxs-lookup"><span data-stu-id="f858c-126">An unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f858c-127">说明</span><span class="sxs-lookup"><span data-stu-id="f858c-127">Remarks</span></span>

<span data-ttu-id="f858c-128">新数组及其数据驻留在通过单个分配创建的缓冲区中, [ScRelocProps](screlocprops.md)函数可用于调整各个[SPropValue](spropvalue.md)结构中的指针。</span><span class="sxs-lookup"><span data-stu-id="f858c-128">The new array and its data reside in a buffer created with a single allocation, and the [ScRelocProps](screlocprops.md) function can be used to adjust the pointers in the individual [SPropValue](spropvalue.md) structures.</span></span> <span data-ttu-id="f858c-129">在此调整之前, 指针有效。</span><span class="sxs-lookup"><span data-stu-id="f858c-129">Prior to this adjustment, the pointers are valid.</span></span> 
  
 <span data-ttu-id="f858c-130">**ScCopyProps**维护复制的属性数组的原始属性顺序。</span><span class="sxs-lookup"><span data-stu-id="f858c-130">**ScCopyProps** maintains the original property order for the copied property array.</span></span> 
  
<span data-ttu-id="f858c-131">_pcb_参数是可选的;如果不为 NULL, 则将其设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="f858c-131">The  _pcb_ parameter is optional; if it is not NULL, it is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f858c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f858c-132">See also</span></span>



[<span data-ttu-id="f858c-133">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="f858c-133">ScDupPropset</span></span>](scduppropset.md)

