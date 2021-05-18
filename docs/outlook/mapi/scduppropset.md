---
title: ScDupPropset
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScDupPropset
api_type:
- COM
ms.assetid: 165ffbd0-54aa-4692-8bd1-09e6ff3762df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77a376bba8d65737be84e2af62e65e0419d20957
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406015"
---
# <a name="scduppropset"></a><span data-ttu-id="d590f-103">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="d590f-103">ScDupPropset</span></span>

  
  
<span data-ttu-id="d590f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d590f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d590f-105">将 [ScCopyProps](sccopyprops.md) 和 [ScCountProps](sccountprops.md) 函数的操作合并在一个 MAPI 内存块中复制属性值数组。</span><span class="sxs-lookup"><span data-stu-id="d590f-105">Duplicates a property value array in a single block of MAPI memory combining the operations of the [ScCopyProps](sccopyprops.md) and [ScCountProps](sccountprops.md) functions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d590f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d590f-106">Header file:</span></span>  <br/> |<span data-ttu-id="d590f-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="d590f-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d590f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d590f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d590f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d590f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d590f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d590f-110">Called by:</span></span>  <br/> |<span data-ttu-id="d590f-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d590f-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScDupPropset(
  int cprop,
  LPSPropValue rgprop,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPSPropValue FAR * prgprop
);
```

## <a name="parameters"></a><span data-ttu-id="d590f-112">参数</span><span class="sxs-lookup"><span data-stu-id="d590f-112">Parameters</span></span>

 <span data-ttu-id="d590f-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="d590f-113">_cprop_</span></span>
  
> <span data-ttu-id="d590f-114">[in]  _rgprop_ 参数指示的数组中的属性值计数。</span><span class="sxs-lookup"><span data-stu-id="d590f-114">[in] Count of property values in the array indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="d590f-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="d590f-115">_rgprop_</span></span>
  
> <span data-ttu-id="d590f-116">[in]指向定义要复制的属性值 [的 SPropValue](spropvalue.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="d590f-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures defining the property values to be duplicated.</span></span> 
    
 <span data-ttu-id="d590f-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="d590f-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="d590f-118">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于为重复的数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="d590f-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory for the duplicated array.</span></span> 
    
 <span data-ttu-id="d590f-119">_prgprop_</span><span class="sxs-lookup"><span data-stu-id="d590f-119">_prgprop_</span></span>
  
> <span data-ttu-id="d590f-120">[out]指向内存中存储返回的 **SPropValue** 结构的重复数组的初始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="d590f-120">[out] Pointer to the initial position in memory where the returned duplicated array of **SPropValue** structures is stored.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d590f-121">返回值</span><span class="sxs-lookup"><span data-stu-id="d590f-121">Return value</span></span>

<span data-ttu-id="d590f-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d590f-122">S_OK</span></span> 
  
> <span data-ttu-id="d590f-123">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="d590f-123">The call succeeded and has returned the expected value or values.</span></span>
    

