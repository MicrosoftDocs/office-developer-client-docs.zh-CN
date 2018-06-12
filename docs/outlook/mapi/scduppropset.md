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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5b93f84026cacd8568dc5ceec5574d144f6d1633
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778705"
---
# <a name="scduppropset"></a><span data-ttu-id="ce537-103">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="ce537-103">ScDupPropset</span></span>

  
  
<span data-ttu-id="ce537-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ce537-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ce537-105">复制一个独立的 MAPI 内存组合的[ScCopyProps](sccopyprops.md)和[ScCountProps](sccountprops.md)函数的操作块中的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="ce537-105">Duplicates a property value array in a single block of MAPI memory combining the operations of the [ScCopyProps](sccopyprops.md) and [ScCountProps](sccountprops.md) functions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ce537-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ce537-106">Header file:</span></span>  <br/> |<span data-ttu-id="ce537-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ce537-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ce537-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ce537-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ce537-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ce537-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ce537-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ce537-110">Called by:</span></span>  <br/> |<span data-ttu-id="ce537-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ce537-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScDupPropset(
  int cprop,
  LPSPropValue rgprop,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPSPropValue FAR * prgprop
);
```

## <a name="parameters"></a><span data-ttu-id="ce537-112">参数</span><span class="sxs-lookup"><span data-stu-id="ce537-112">Parameters</span></span>

 <span data-ttu-id="ce537-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="ce537-113">_cprop_</span></span>
  
> <span data-ttu-id="ce537-114">[in]由_rgprop_参数指示在阵列中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="ce537-114">[in] Count of property values in the array indicated by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="ce537-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="ce537-115">_rgprop_</span></span>
  
> <span data-ttu-id="ce537-116">[in]指向[SPropValue](spropvalue.md)结构定义要重复的属性值的数组。</span><span class="sxs-lookup"><span data-stu-id="ce537-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures defining the property values to be duplicated.</span></span> 
    
 <span data-ttu-id="ce537-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="ce537-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="ce537-118">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于重复数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="ce537-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory for the duplicated array.</span></span> 
    
 <span data-ttu-id="ce537-119">_prgprop_</span><span class="sxs-lookup"><span data-stu-id="ce537-119">_prgprop_</span></span>
  
> <span data-ttu-id="ce537-120">[输出]为在内存中存储的**SPropValue**结构重复返回的数组的初始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="ce537-120">[out] Pointer to the initial position in memory where the returned duplicated array of **SPropValue** structures is stored.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ce537-121">返回值</span><span class="sxs-lookup"><span data-stu-id="ce537-121">Return value</span></span>

<span data-ttu-id="ce537-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce537-122">S_OK</span></span> 
  
> <span data-ttu-id="ce537-123">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="ce537-123">The call succeeded and has returned the expected value or values.</span></span>
    

