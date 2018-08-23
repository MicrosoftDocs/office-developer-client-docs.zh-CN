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
ms.openlocfilehash: 635525a1c2c3234d724534d225eb07022afc9956
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592120"
---
# <a name="propcopymore"></a><span data-ttu-id="eabb3-103">PropCopyMore</span><span class="sxs-lookup"><span data-stu-id="eabb3-103">PropCopyMore</span></span>

  
  
<span data-ttu-id="eabb3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eabb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eabb3-105">将单个属性值从源位置复制到目标位置。</span><span class="sxs-lookup"><span data-stu-id="eabb3-105">Copies a single property value from a source location to a destination location.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="eabb3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="eabb3-106">Header file:</span></span>  <br/> |<span data-ttu-id="eabb3-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="eabb3-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="eabb3-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="eabb3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="eabb3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="eabb3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="eabb3-110">调用：</span><span class="sxs-lookup"><span data-stu-id="eabb3-110">Called by:</span></span>  <br/> |<span data-ttu-id="eabb3-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="eabb3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE PropCopyMore(
  LPSPropValue lpSPropValueDest,
  LPSPropValue lpSPropValueSrc,
  ALLOCATEMORE * lpfAllocMore,
  LPVOID lpvObject
);
```

## <a name="parameters"></a><span data-ttu-id="eabb3-112">参数</span><span class="sxs-lookup"><span data-stu-id="eabb3-112">Parameters</span></span>

 <span data-ttu-id="eabb3-113">_lpSPropValueDest_</span><span class="sxs-lookup"><span data-stu-id="eabb3-113">_lpSPropValueDest_</span></span>
  
> <span data-ttu-id="eabb3-114">[输出]此函数向其中写入定义复制的属性值的[SPropValue](spropvalue.md)结构的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="eabb3-114">[out] Pointer to the location to which this function writes an [SPropValue](spropvalue.md) structure defining the copied property value.</span></span> 
    
 <span data-ttu-id="eabb3-115">_lpSPropValueSrc_</span><span class="sxs-lookup"><span data-stu-id="eabb3-115">_lpSPropValueSrc_</span></span>
  
> <span data-ttu-id="eabb3-116">[in]指向包含属性值将复制的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="eabb3-116">[in] Pointer to the [SPropValue](spropvalue.md) structure that contains the property value to be copied.</span></span> 
    
 <span data-ttu-id="eabb3-117">_lpfAllocMore_</span><span class="sxs-lookup"><span data-stu-id="eabb3-117">_lpfAllocMore_</span></span>
  
> <span data-ttu-id="eabb3-118">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存，如果目标位置没有足够容纳要复制的属性。</span><span class="sxs-lookup"><span data-stu-id="eabb3-118">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function to be used to allocate additional memory if the destination location is not large enough to hold the property to be copied.</span></span> 
    
 <span data-ttu-id="eabb3-119">_lpvObject_</span><span class="sxs-lookup"><span data-stu-id="eabb3-119">_lpvObject_</span></span>
  
> <span data-ttu-id="eabb3-120">[in]指向其**MAPIAllocateMore**将分配空间必要对象的指针。</span><span class="sxs-lookup"><span data-stu-id="eabb3-120">[in] Pointer to an object for which **MAPIAllocateMore** will allocate space if necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="eabb3-121">返回值</span><span class="sxs-lookup"><span data-stu-id="eabb3-121">Return value</span></span>

<span data-ttu-id="eabb3-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="eabb3-122">S_OK</span></span>
  
> <span data-ttu-id="eabb3-123">已成功复制单个属性值。</span><span class="sxs-lookup"><span data-stu-id="eabb3-123">The single property value was copied successfully.</span></span>
    
<span data-ttu-id="eabb3-124">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="eabb3-124">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="eabb3-125">遇到了未知的属性类型。</span><span class="sxs-lookup"><span data-stu-id="eabb3-125">An unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="eabb3-126">注解</span><span class="sxs-lookup"><span data-stu-id="eabb3-126">Remarks</span></span>

<span data-ttu-id="eabb3-127">客户端应用程序或服务提供商可以使用**PropCopyMore**函数复制超出将释放才能在其他地方使用它的表的属性。</span><span class="sxs-lookup"><span data-stu-id="eabb3-127">A client application or service provider can use the **PropCopyMore** function to copy a property out of a table that is about to be freed in order to use it elsewhere.</span></span> 
  
 <span data-ttu-id="eabb3-128">**PropCopyMore**不需要除非复制该属性值的类型，如 PT_STRING8，不适合[SPropValue](spropvalue.md)结构中的分配内存。</span><span class="sxs-lookup"><span data-stu-id="eabb3-128">**PropCopyMore** does not need to allocate memory unless the property value copied is of a type, such as PT_STRING8, that does not fit in an [SPropValue](spropvalue.md) structure.</span></span> <span data-ttu-id="eabb3-129">对于这些大型属性，该函数分配内存使用指将指针传递_lpfAllocMore_参数中的[MAPIAllocateMore](mapiallocatemore.md)函数。</span><span class="sxs-lookup"><span data-stu-id="eabb3-129">For these large properties, the function allocates memory using the [MAPIAllocateMore](mapiallocatemore.md) function to which a pointer is passed in the  _lpfAllocMore_ parameter.</span></span> 
  
<span data-ttu-id="eabb3-130">Injudicious 利用**PropCopyMore**片段内存;考虑使用[ScCopyProps](sccopyprops.md)函数。</span><span class="sxs-lookup"><span data-stu-id="eabb3-130">Injudicious use of **PropCopyMore** fragments memory; consider using the [ScCopyProps](sccopyprops.md) function instead.</span></span> 
  

