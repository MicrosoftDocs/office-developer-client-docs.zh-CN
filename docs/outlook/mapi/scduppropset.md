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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351266"
---
# <a name="scduppropset"></a><span data-ttu-id="d2506-103">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="d2506-103">ScDupPropset</span></span>

  
  
<span data-ttu-id="d2506-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2506-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2506-105">在单个 MAPI 内存块中复制属性值数组, 以组合[ScCopyProps](sccopyprops.md)和[ScCountProps](sccountprops.md)函数的操作。</span><span class="sxs-lookup"><span data-stu-id="d2506-105">Duplicates a property value array in a single block of MAPI memory combining the operations of the [ScCopyProps](sccopyprops.md) and [ScCountProps](sccountprops.md) functions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d2506-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d2506-106">Header file:</span></span>  <br/> |<span data-ttu-id="d2506-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="d2506-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d2506-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d2506-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d2506-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d2506-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d2506-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d2506-110">Called by:</span></span>  <br/> |<span data-ttu-id="d2506-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d2506-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScDupPropset(
  int cprop,
  LPSPropValue rgprop,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPSPropValue FAR * prgprop
);
```

## <a name="parameters"></a><span data-ttu-id="d2506-112">参数</span><span class="sxs-lookup"><span data-stu-id="d2506-112">Parameters</span></span>

 <span data-ttu-id="d2506-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="d2506-113">_cprop_</span></span>
  
> <span data-ttu-id="d2506-114">实时由_rgprop_参数指示的数组中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="d2506-114">[in] Count of property values in the array indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="d2506-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="d2506-115">_rgprop_</span></span>
  
> <span data-ttu-id="d2506-116">实时指向定义要复制的属性值的[SPropValue](spropvalue.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="d2506-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures defining the property values to be duplicated.</span></span> 
    
 <span data-ttu-id="d2506-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="d2506-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="d2506-118">实时指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针, 该函数用于为重复的数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="d2506-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory for the duplicated array.</span></span> 
    
 <span data-ttu-id="d2506-119">_prgprop_</span><span class="sxs-lookup"><span data-stu-id="d2506-119">_prgprop_</span></span>
  
> <span data-ttu-id="d2506-120">排除指向存储返回的**SPropValue**结构的重复数组的内存中的初始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="d2506-120">[out] Pointer to the initial position in memory where the returned duplicated array of **SPropValue** structures is stored.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d2506-121">返回值</span><span class="sxs-lookup"><span data-stu-id="d2506-121">Return value</span></span>

<span data-ttu-id="d2506-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2506-122">S_OK</span></span> 
  
> <span data-ttu-id="d2506-123">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="d2506-123">The call succeeded and has returned the expected value or values.</span></span>
    

