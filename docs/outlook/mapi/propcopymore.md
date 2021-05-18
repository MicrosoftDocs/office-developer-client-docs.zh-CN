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
# <a name="propcopymore"></a><span data-ttu-id="ee328-103">PropCopyMore</span><span class="sxs-lookup"><span data-stu-id="ee328-103">PropCopyMore</span></span>

  
  
<span data-ttu-id="ee328-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee328-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee328-105">将单个属性值从源位置复制到目标位置。</span><span class="sxs-lookup"><span data-stu-id="ee328-105">Copies a single property value from a source location to a destination location.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ee328-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ee328-106">Header file:</span></span>  <br/> |<span data-ttu-id="ee328-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ee328-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ee328-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ee328-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ee328-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ee328-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ee328-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ee328-110">Called by:</span></span>  <br/> |<span data-ttu-id="ee328-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ee328-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE PropCopyMore(
  LPSPropValue lpSPropValueDest,
  LPSPropValue lpSPropValueSrc,
  ALLOCATEMORE * lpfAllocMore,
  LPVOID lpvObject
);
```

## <a name="parameters"></a><span data-ttu-id="ee328-112">参数</span><span class="sxs-lookup"><span data-stu-id="ee328-112">Parameters</span></span>

 <span data-ttu-id="ee328-113">_lpSPropValueDest_</span><span class="sxs-lookup"><span data-stu-id="ee328-113">_lpSPropValueDest_</span></span>
  
> <span data-ttu-id="ee328-114">[out]指向此函数写入定义复制属性值 [的 SPropValue](spropvalue.md) 结构的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="ee328-114">[out] Pointer to the location to which this function writes an [SPropValue](spropvalue.md) structure defining the copied property value.</span></span> 
    
 <span data-ttu-id="ee328-115">_lpSPropValueSrc_</span><span class="sxs-lookup"><span data-stu-id="ee328-115">_lpSPropValueSrc_</span></span>
  
> <span data-ttu-id="ee328-116">[in]指向包含要复制的属性值的 [SPropValue](spropvalue.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ee328-116">[in] Pointer to the [SPropValue](spropvalue.md) structure that contains the property value to be copied.</span></span> 
    
 <span data-ttu-id="ee328-117">_lpfAllocMore_</span><span class="sxs-lookup"><span data-stu-id="ee328-117">_lpfAllocMore_</span></span>
  
> <span data-ttu-id="ee328-118">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，当目标位置不足以容纳要复制的属性时，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="ee328-118">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function to be used to allocate additional memory if the destination location is not large enough to hold the property to be copied.</span></span> 
    
 <span data-ttu-id="ee328-119">_lpvObject_</span><span class="sxs-lookup"><span data-stu-id="ee328-119">_lpvObject_</span></span>
  
> <span data-ttu-id="ee328-120">[in]指向 **MAPIAllocateMore** 将在必要时为其分配空间的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ee328-120">[in] Pointer to an object for which **MAPIAllocateMore** will allocate space if necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ee328-121">返回值</span><span class="sxs-lookup"><span data-stu-id="ee328-121">Return value</span></span>

<span data-ttu-id="ee328-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee328-122">S_OK</span></span>
  
> <span data-ttu-id="ee328-123">已成功复制单个属性值。</span><span class="sxs-lookup"><span data-stu-id="ee328-123">The single property value was copied successfully.</span></span>
    
<span data-ttu-id="ee328-124">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ee328-124">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="ee328-125">遇到未知属性类型。</span><span class="sxs-lookup"><span data-stu-id="ee328-125">An unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ee328-126">备注</span><span class="sxs-lookup"><span data-stu-id="ee328-126">Remarks</span></span>

<span data-ttu-id="ee328-127">客户端应用程序或服务提供商可以使用 **PropCopyMore** 函数从即将释放的表中复制属性，以便将其用于其他位置。</span><span class="sxs-lookup"><span data-stu-id="ee328-127">A client application or service provider can use the **PropCopyMore** function to copy a property out of a table that is about to be freed in order to use it elsewhere.</span></span> 
  
 <span data-ttu-id="ee328-128">**PropCopyMore** 不需要分配内存，除非复制的属性值的类型（如 PT_STRING8）不适合 [SPropValue](spropvalue.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="ee328-128">**PropCopyMore** does not need to allocate memory unless the property value copied is of a type, such as PT_STRING8, that does not fit in an [SPropValue](spropvalue.md) structure.</span></span> <span data-ttu-id="ee328-129">对于这些大型属性，该函数使用 [MAPIAllocateMore](mapiallocatemore.md) 函数分配内存，其中一个指针将传递到  _lpfAllocMore_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="ee328-129">For these large properties, the function allocates memory using the [MAPIAllocateMore](mapiallocatemore.md) function to which a pointer is passed in the  _lpfAllocMore_ parameter.</span></span> 
  
<span data-ttu-id="ee328-130">不等同地使用 **PropCopyMore** 片段内存;请考虑改为使用 [ScCopyProps](sccopyprops.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="ee328-130">Injudicious use of **PropCopyMore** fragments memory; consider using the [ScCopyProps](sccopyprops.md) function instead.</span></span> 
  

