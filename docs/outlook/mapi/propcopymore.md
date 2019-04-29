---
title: PropCopyMore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PropCopyMore
api_type:
- HeaderDef
ms.assetid: 133d47cf-3592-44f3-8cdd-be402d160ee4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 827cdb919499a068f7932d8f1f7ec264ddc5b47c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404468"
---
# <a name="propcopymore"></a><span data-ttu-id="7fc95-103">PropCopyMore</span><span class="sxs-lookup"><span data-stu-id="7fc95-103">PropCopyMore</span></span>

  
  
<span data-ttu-id="7fc95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7fc95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7fc95-105">将单个属性值从源位置复制到目标位置。</span><span class="sxs-lookup"><span data-stu-id="7fc95-105">Copies a single property value from a source location to a destination location.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7fc95-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7fc95-106">Header file:</span></span>  <br/> |<span data-ttu-id="7fc95-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="7fc95-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7fc95-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7fc95-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7fc95-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7fc95-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7fc95-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7fc95-110">Called by:</span></span>  <br/> |<span data-ttu-id="7fc95-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="7fc95-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE PropCopyMore(
  LPSPropValue lpSPropValueDest,
  LPSPropValue lpSPropValueSrc,
  ALLOCATEMORE * lpfAllocMore,
  LPVOID lpvObject
);
```

## <a name="parameters"></a><span data-ttu-id="7fc95-112">参数</span><span class="sxs-lookup"><span data-stu-id="7fc95-112">Parameters</span></span>

 <span data-ttu-id="7fc95-113">_lpSPropValueDest_</span><span class="sxs-lookup"><span data-stu-id="7fc95-113">_lpSPropValueDest_</span></span>
  
> <span data-ttu-id="7fc95-114">排除指向此函数将定义复制的属性值的[SPropValue](spropvalue.md)结构写入到的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="7fc95-114">[out] Pointer to the location to which this function writes an [SPropValue](spropvalue.md) structure defining the copied property value.</span></span> 
    
 <span data-ttu-id="7fc95-115">_lpSPropValueSrc_</span><span class="sxs-lookup"><span data-stu-id="7fc95-115">_lpSPropValueSrc_</span></span>
  
> <span data-ttu-id="7fc95-116">实时指向[SPropValue](spropvalue.md)结构的指针, 该结构包含要复制的属性值。</span><span class="sxs-lookup"><span data-stu-id="7fc95-116">[in] Pointer to the [SPropValue](spropvalue.md) structure that contains the property value to be copied.</span></span> 
    
 <span data-ttu-id="7fc95-117">_lpfAllocMore_</span><span class="sxs-lookup"><span data-stu-id="7fc95-117">_lpfAllocMore_</span></span>
  
> <span data-ttu-id="7fc95-118">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于在目标位置的大小不足以容纳要复制的属性时分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="7fc95-118">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function to be used to allocate additional memory if the destination location is not large enough to hold the property to be copied.</span></span> 
    
 <span data-ttu-id="7fc95-119">_lpvObject_</span><span class="sxs-lookup"><span data-stu-id="7fc95-119">_lpvObject_</span></span>
  
> <span data-ttu-id="7fc95-120">实时指向**MAPIAllocateMore**将在必要时为其分配空间的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7fc95-120">[in] Pointer to an object for which **MAPIAllocateMore** will allocate space if necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7fc95-121">返回值</span><span class="sxs-lookup"><span data-stu-id="7fc95-121">Return value</span></span>

<span data-ttu-id="7fc95-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fc95-122">S_OK</span></span>
  
> <span data-ttu-id="7fc95-123">已成功复制单个属性值。</span><span class="sxs-lookup"><span data-stu-id="7fc95-123">The single property value was copied successfully.</span></span>
    
<span data-ttu-id="7fc95-124">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="7fc95-124">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="7fc95-125">遇到未知的属性类型。</span><span class="sxs-lookup"><span data-stu-id="7fc95-125">An unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7fc95-126">说明</span><span class="sxs-lookup"><span data-stu-id="7fc95-126">Remarks</span></span>

<span data-ttu-id="7fc95-127">客户端应用程序或服务提供程序可以使用**PropCopyMore**函数复制即将释放的表的属性, 以便在其他位置使用该属性。</span><span class="sxs-lookup"><span data-stu-id="7fc95-127">A client application or service provider can use the **PropCopyMore** function to copy a property out of a table that is about to be freed in order to use it elsewhere.</span></span> 
  
 <span data-ttu-id="7fc95-128">**PropCopyMore**不需要分配内存, 除非复制的属性值的类型 (如 PT_STRING8) 不能包含在[SPropValue](spropvalue.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="7fc95-128">**PropCopyMore** does not need to allocate memory unless the property value copied is of a type, such as PT_STRING8, that does not fit in an [SPropValue](spropvalue.md) structure.</span></span> <span data-ttu-id="7fc95-129">对于这些大型属性, 函数使用在_lpfAllocMore_参数中传递指针的[MAPIAllocateMore](mapiallocatemore.md)函数分配内存。</span><span class="sxs-lookup"><span data-stu-id="7fc95-129">For these large properties, the function allocates memory using the [MAPIAllocateMore](mapiallocatemore.md) function to which a pointer is passed in the  _lpfAllocMore_ parameter.</span></span> 
  
<span data-ttu-id="7fc95-130">Injudicious 使用**PropCopyMore**分段内存;请考虑改用[ScCopyProps](sccopyprops.md)函数。</span><span class="sxs-lookup"><span data-stu-id="7fc95-130">Injudicious use of **PropCopyMore** fragments memory; consider using the [ScCopyProps](sccopyprops.md) function instead.</span></span> 
  

