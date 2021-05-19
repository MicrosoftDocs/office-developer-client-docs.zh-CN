---
title: ScRelocProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScRelocProps
api_type:
- COM
ms.assetid: 4aafb254-6074-4a7c-b915-d3d33304ac38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c73fb96c9620a90ab0505b394fcb9853d02dcde5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421086"
---
# <a name="screlocprops"></a><span data-ttu-id="6e75b-103">ScRelocProps</span><span class="sxs-lookup"><span data-stu-id="6e75b-103">ScRelocProps</span></span>

  
  
<span data-ttu-id="6e75b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e75b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e75b-105">在数组及其数据被复制或移动到新位置之后，调整 [SPropValue](spropvalue.md) 数组中的指针。</span><span class="sxs-lookup"><span data-stu-id="6e75b-105">Adjusts the pointers in an [SPropValue](spropvalue.md) array after the array and its data have been copied or moved to a new location.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6e75b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6e75b-106">Header file:</span></span>  <br/> |<span data-ttu-id="6e75b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6e75b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="6e75b-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="6e75b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6e75b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6e75b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6e75b-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="6e75b-110">Called by:</span></span>  <br/> |<span data-ttu-id="6e75b-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="6e75b-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScRelocProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="6e75b-112">参数</span><span class="sxs-lookup"><span data-stu-id="6e75b-112">Parameters</span></span>

 <span data-ttu-id="6e75b-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="6e75b-113">_cprop_</span></span>
  
> <span data-ttu-id="6e75b-114">[in]  _rgprop_ 参数指向的数组中的属性计数。</span><span class="sxs-lookup"><span data-stu-id="6e75b-114">[in] Count of properties in the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="6e75b-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="6e75b-115">_rgprop_</span></span>
  
> <span data-ttu-id="6e75b-116">[in]指向要调整指针 [的 SPropValue](spropvalue.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="6e75b-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures for which pointers are to be adjusted.</span></span> 
    
 <span data-ttu-id="6e75b-117">_pvBaseOld_</span><span class="sxs-lookup"><span data-stu-id="6e75b-117">_pvBaseOld_</span></span>
  
> <span data-ttu-id="6e75b-118">[in]指向 rgprop 参数指向的数组的原始  _基地址的_ 指针。</span><span class="sxs-lookup"><span data-stu-id="6e75b-118">[in] Pointer to the original base address of the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="6e75b-119">_pvBaseNew_</span><span class="sxs-lookup"><span data-stu-id="6e75b-119">_pvBaseNew_</span></span>
  
> <span data-ttu-id="6e75b-120">[in]指向  _rgprop_ 参数指向的数组的新基地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6e75b-120">[in] Pointer to the new base address of the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="6e75b-121">_这些_</span><span class="sxs-lookup"><span data-stu-id="6e75b-121">_pcb_</span></span>
  
> <span data-ttu-id="6e75b-122">[in， out]指向  _pvBaseNew_ 参数指示的数组大小的可选指针（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6e75b-122">[in, out] Optional pointer to the size, in bytes, of the array indicated by the  _pvBaseNew_ parameter.</span></span> <span data-ttu-id="6e75b-123">如果不为 NULL，  _则将 pv_ 参数设置为  _pvD_ 参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="6e75b-123">If not NULL, the  _pcb_ parameter is set to the number of bytes stored in the  _pvD_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6e75b-124">返回值</span><span class="sxs-lookup"><span data-stu-id="6e75b-124">Return value</span></span>

<span data-ttu-id="6e75b-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e75b-125">S_OK</span></span>
  
> <span data-ttu-id="6e75b-126">指针已成功调整。</span><span class="sxs-lookup"><span data-stu-id="6e75b-126">Pointers were adjusted successfully.</span></span>
    
<span data-ttu-id="6e75b-127">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="6e75b-127">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="6e75b-128">一个或两个参数无效，或遇到未知属性类型。</span><span class="sxs-lookup"><span data-stu-id="6e75b-128">One or both parameters were invalid, or an unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e75b-129">备注</span><span class="sxs-lookup"><span data-stu-id="6e75b-129">Remarks</span></span>

<span data-ttu-id="6e75b-130">**ScRelocProps** 函数的运行假设是最初在类似于 **对 ScCopyProps** 函数的调用的单个调用中分配了调整指针的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="6e75b-130">The **ScRelocProps** function operates on the assumption that the property value array for which pointers are adjusted was originally allocated in a single call similar to a call to the **ScCopyProps** function.</span></span> <span data-ttu-id="6e75b-131">如果客户端应用程序或服务提供商使用从脱节的内存块构建的属性值，则它应改为使用 [ScCopyProps](sccopyprops.md) 复制属性。</span><span class="sxs-lookup"><span data-stu-id="6e75b-131">If a client application or service provider is working with a property value that is built from disjointed blocks of memory, it should use [ScCopyProps](sccopyprops.md) to copy properties instead.</span></span> 
  
 <span data-ttu-id="6e75b-132">**ScRelocProps** 用于维护 [SPropValue](spropvalue.md) 数组中指针的有效性。</span><span class="sxs-lookup"><span data-stu-id="6e75b-132">**ScRelocProps** is used to maintain the validity of pointers in an [SPropValue](spropvalue.md) array.</span></span> <span data-ttu-id="6e75b-133">若要在将此类数组写入磁盘并读取磁盘时保持指针的有效性，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6e75b-133">To maintain pointers' validity when writing such an array to and reading it from a disk, perform the following operations:</span></span> 
  
1. <span data-ttu-id="6e75b-134">在将数组和数据写入磁盘之前，请对数组调用 **ScRelocProps，** 其中  _pvBaseNew_ 参数指向一些标准值零，例如。</span><span class="sxs-lookup"><span data-stu-id="6e75b-134">Before writing the array and data to a disk, call **ScRelocProps** on the array with the  _pvBaseNew_ parameter pointing to some standard value zero, for instance.</span></span> 
    
2. <span data-ttu-id="6e75b-135">从磁盘读取数组和数据后，对 _pvBaseOld_ 参数等于步骤 1 中使用的相同标准值的数组调用 **ScRelocProps。**</span><span class="sxs-lookup"><span data-stu-id="6e75b-135">After reading the array and data from a disk, call **ScRelocProps** on the array with the  _pvBaseOld_ parameter equal to the same standard value used in Step 1.</span></span> <span data-ttu-id="6e75b-136">必须将数组和数据读取到通过单个分配创建的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="6e75b-136">The array and data must be read into a buffer created with a single allocation.</span></span> 
    
3. <span data-ttu-id="6e75b-137">**ScRelocProps** 的 _为可选_ 参数。</span><span class="sxs-lookup"><span data-stu-id="6e75b-137">The  _pcb_ parameter to **ScRelocProps** is optional.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6e75b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e75b-138">See also</span></span>



[<span data-ttu-id="6e75b-139">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6e75b-139">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="6e75b-140">ScCountProps</span><span class="sxs-lookup"><span data-stu-id="6e75b-140">ScCountProps</span></span>](sccountprops.md)
  
[<span data-ttu-id="6e75b-141">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="6e75b-141">ScDupPropset</span></span>](scduppropset.md)
  
[<span data-ttu-id="6e75b-142">ScRelocNotifications</span><span class="sxs-lookup"><span data-stu-id="6e75b-142">ScRelocNotifications</span></span>](screlocnotifications.md)

