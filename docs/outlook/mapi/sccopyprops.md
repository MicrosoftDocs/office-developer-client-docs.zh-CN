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
ms.openlocfilehash: 979415f1d792f92e593a7073cc84cfd6ba832b6c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778683"
---
# <a name="sccopyprops"></a><span data-ttu-id="a169d-103">ScCopyProps</span><span class="sxs-lookup"><span data-stu-id="a169d-103">ScCopyProps</span></span>

  
  
<span data-ttu-id="a169d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a169d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a169d-105">复制到新目标[SPropValue](spropvalue.md)结构的数组定义的属性。</span><span class="sxs-lookup"><span data-stu-id="a169d-105">Copies the properties defined by an array of [SPropValue](spropvalue.md) structures to a new destination.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a169d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a169d-106">Header file:</span></span>  <br/> |<span data-ttu-id="a169d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a169d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a169d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a169d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a169d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a169d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a169d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a169d-110">Called by:</span></span>  <br/> |<span data-ttu-id="a169d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a169d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCopyProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="a169d-112">参数</span><span class="sxs-lookup"><span data-stu-id="a169d-112">Parameters</span></span>

 <span data-ttu-id="a169d-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="a169d-113">_cprop_</span></span>
  
> <span data-ttu-id="a169d-114">[in]要复制的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="a169d-114">[in] Count of properties to be copied.</span></span> 
    
 <span data-ttu-id="a169d-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="a169d-115">_rgprop_</span></span>
  
> <span data-ttu-id="a169d-116">[in]为数组定义要复制的属性的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a169d-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures that define the properties to be copied.</span></span> <span data-ttu-id="a169d-117">_Rgprop_参数没有为指向开始的数组，但它必须指向某数组中的**SPropValue**结构开始处。</span><span class="sxs-lookup"><span data-stu-id="a169d-117">The  _rgprop_ parameter does not have to point to the beginning of the array, but it must point to the beginning of one of the **SPropValue** structures in the array.</span></span> 
    
 <span data-ttu-id="a169d-118">_pvDst_</span><span class="sxs-lookup"><span data-stu-id="a169d-118">_pvDst_</span></span>
  
> <span data-ttu-id="a169d-119">[in]指向此函数将属性复制到内存中的初始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="a169d-119">[in] Pointer to the initial position in memory to which this function copies the properties.</span></span> 
    
 <span data-ttu-id="a169d-120">_pcb_</span><span class="sxs-lookup"><span data-stu-id="a169d-120">_pcb_</span></span>
  
> <span data-ttu-id="a169d-121">[输出]指向的大小，以字节为单位的内存_pvDst_参数指向的块的可选指针。</span><span class="sxs-lookup"><span data-stu-id="a169d-121">[out] Optional pointer to the size, in bytes, of the block of memory pointed to by the  _pvDst_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a169d-122">返回值</span><span class="sxs-lookup"><span data-stu-id="a169d-122">Return value</span></span>

<span data-ttu-id="a169d-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="a169d-123">S_OK</span></span>
  
> <span data-ttu-id="a169d-124">已成功复制属性。</span><span class="sxs-lookup"><span data-stu-id="a169d-124">Properties were copied successfully.</span></span>
    
<span data-ttu-id="a169d-125">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="a169d-125">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="a169d-126">遇到了未知的属性类型。</span><span class="sxs-lookup"><span data-stu-id="a169d-126">An unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a169d-127">说明</span><span class="sxs-lookup"><span data-stu-id="a169d-127">Remarks</span></span>

<span data-ttu-id="a169d-128">新的数组和其数据驻留在创建一个分配，与缓冲区和[ScRelocProps](screlocprops.md)函数可用于调整中的单个[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a169d-128">The new array and its data reside in a buffer created with a single allocation, and the [ScRelocProps](screlocprops.md) function can be used to adjust the pointers in the individual [SPropValue](spropvalue.md) structures.</span></span> <span data-ttu-id="a169d-129">在此调整之前, 指针是有效。</span><span class="sxs-lookup"><span data-stu-id="a169d-129">Prior to this adjustment, the pointers are valid.</span></span> 
  
 <span data-ttu-id="a169d-130">**ScCopyProps**维持复制的属性数组的原始属性顺序。</span><span class="sxs-lookup"><span data-stu-id="a169d-130">**ScCopyProps** maintains the original property order for the copied property array.</span></span> 
  
<span data-ttu-id="a169d-131">_Pcb_参数是可选的。如果不为 NULL，则将其设置为_pvDst_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="a169d-131">The  _pcb_ parameter is optional; if it is not NULL, it is set to the number of bytes stored in the  _pvDst_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a169d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a169d-132">See also</span></span>



[<span data-ttu-id="a169d-133">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="a169d-133">ScDupPropset</span></span>](scduppropset.md)

