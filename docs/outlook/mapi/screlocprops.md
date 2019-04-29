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
# <a name="screlocprops"></a><span data-ttu-id="84c28-103">ScRelocProps</span><span class="sxs-lookup"><span data-stu-id="84c28-103">ScRelocProps</span></span>

  
  
<span data-ttu-id="84c28-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84c28-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84c28-105">在将数组及其数据复制或移动到新位置之后, 调整[SPropValue](spropvalue.md)数组中的指针。</span><span class="sxs-lookup"><span data-stu-id="84c28-105">Adjusts the pointers in an [SPropValue](spropvalue.md) array after the array and its data have been copied or moved to a new location.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="84c28-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="84c28-106">Header file:</span></span>  <br/> |<span data-ttu-id="84c28-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="84c28-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="84c28-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="84c28-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="84c28-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="84c28-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="84c28-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="84c28-110">Called by:</span></span>  <br/> |<span data-ttu-id="84c28-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="84c28-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScRelocProps(
  int cprop,
  LPSPropValue rgprop,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a><span data-ttu-id="84c28-112">参数</span><span class="sxs-lookup"><span data-stu-id="84c28-112">Parameters</span></span>

 <span data-ttu-id="84c28-113">_cprop_</span><span class="sxs-lookup"><span data-stu-id="84c28-113">_cprop_</span></span>
  
> <span data-ttu-id="84c28-114">实时由_rgprop_参数指向的数组中的属性计数。</span><span class="sxs-lookup"><span data-stu-id="84c28-114">[in] Count of properties in the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="84c28-115">_rgprop_</span><span class="sxs-lookup"><span data-stu-id="84c28-115">_rgprop_</span></span>
  
> <span data-ttu-id="84c28-116">实时指向要调整其指针的[SPropValue](spropvalue.md)结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="84c28-116">[in] Pointer to an array of [SPropValue](spropvalue.md) structures for which pointers are to be adjusted.</span></span> 
    
 <span data-ttu-id="84c28-117">_pvBaseOld_</span><span class="sxs-lookup"><span data-stu-id="84c28-117">_pvBaseOld_</span></span>
  
> <span data-ttu-id="84c28-118">实时指向由_rgprop_参数指向的数组的原始基址的指针。</span><span class="sxs-lookup"><span data-stu-id="84c28-118">[in] Pointer to the original base address of the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="84c28-119">_pvBaseNew_</span><span class="sxs-lookup"><span data-stu-id="84c28-119">_pvBaseNew_</span></span>
  
> <span data-ttu-id="84c28-120">实时指向_rgprop_参数指向的数组的新基址的指针。</span><span class="sxs-lookup"><span data-stu-id="84c28-120">[in] Pointer to the new base address of the array pointed to by the  _rgprop_ parameter.</span></span> 
    
 <span data-ttu-id="84c28-121">_pcb_</span><span class="sxs-lookup"><span data-stu-id="84c28-121">_pcb_</span></span>
  
> <span data-ttu-id="84c28-122">[in, out]可选指针, 指向由_pvBaseNew_参数指示的数组的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="84c28-122">[in, out] Optional pointer to the size, in bytes, of the array indicated by the  _pvBaseNew_ parameter.</span></span> <span data-ttu-id="84c28-123">如果不为 NULL, 则将_pcb_参数设置为_pvD_参数中存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="84c28-123">If not NULL, the  _pcb_ parameter is set to the number of bytes stored in the  _pvD_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="84c28-124">返回值</span><span class="sxs-lookup"><span data-stu-id="84c28-124">Return value</span></span>

<span data-ttu-id="84c28-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="84c28-125">S_OK</span></span>
  
> <span data-ttu-id="84c28-126">已成功调整指针。</span><span class="sxs-lookup"><span data-stu-id="84c28-126">Pointers were adjusted successfully.</span></span>
    
<span data-ttu-id="84c28-127">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="84c28-127">MAPI_E_INVALID_PARAMETER</span></span>
  
> <span data-ttu-id="84c28-128">一个或两个参数无效, 或者遇到未知的属性类型。</span><span class="sxs-lookup"><span data-stu-id="84c28-128">One or both parameters were invalid, or an unknown property type was encountered.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="84c28-129">说明</span><span class="sxs-lookup"><span data-stu-id="84c28-129">Remarks</span></span>

<span data-ttu-id="84c28-130">**ScRelocProps**函数在假设您对其调整指针的属性值数组进行操作时, 最初是在与**ScCopyProps**函数的调用类似的单个调用中分配的。</span><span class="sxs-lookup"><span data-stu-id="84c28-130">The **ScRelocProps** function operates on the assumption that the property value array for which pointers are adjusted was originally allocated in a single call similar to a call to the **ScCopyProps** function.</span></span> <span data-ttu-id="84c28-131">如果客户端应用程序或服务提供程序正在使用从脱节内存块生成的属性值, 则应改用[ScCopyProps](sccopyprops.md)复制属性。</span><span class="sxs-lookup"><span data-stu-id="84c28-131">If a client application or service provider is working with a property value that is built from disjointed blocks of memory, it should use [ScCopyProps](sccopyprops.md) to copy properties instead.</span></span> 
  
 <span data-ttu-id="84c28-132">**ScRelocProps**用于维护[SPropValue](spropvalue.md)数组中的指针的有效性。</span><span class="sxs-lookup"><span data-stu-id="84c28-132">**ScRelocProps** is used to maintain the validity of pointers in an [SPropValue](spropvalue.md) array.</span></span> <span data-ttu-id="84c28-133">若要在将此类数组写入和读取磁盘时保持指针的有效性, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="84c28-133">To maintain pointers' validity when writing such an array to and reading it from a disk, perform the following operations:</span></span> 
  
1. <span data-ttu-id="84c28-134">在将数组和数据写入磁盘之前, 请使用_pvBaseNew_参数指向某个标准值零对数组调用**ScRelocProps** , 例如。</span><span class="sxs-lookup"><span data-stu-id="84c28-134">Before writing the array and data to a disk, call **ScRelocProps** on the array with the  _pvBaseNew_ parameter pointing to some standard value zero, for instance.</span></span> 
    
2. <span data-ttu-id="84c28-135">在从磁盘读取数组和数据之后, 对阵列调用**ScRelocProps** , 将_pvBaseOld_参数等于与步骤1中使用的相同标准值。</span><span class="sxs-lookup"><span data-stu-id="84c28-135">After reading the array and data from a disk, call **ScRelocProps** on the array with the  _pvBaseOld_ parameter equal to the same standard value used in Step 1.</span></span> <span data-ttu-id="84c28-136">必须将数组和数据读入单个分配中创建的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="84c28-136">The array and data must be read into a buffer created with a single allocation.</span></span> 
    
3. <span data-ttu-id="84c28-137">**ScRelocProps**的_pcb_参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="84c28-137">The  _pcb_ parameter to **ScRelocProps** is optional.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="84c28-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84c28-138">See also</span></span>



[<span data-ttu-id="84c28-139">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="84c28-139">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="84c28-140">ScCountProps</span><span class="sxs-lookup"><span data-stu-id="84c28-140">ScCountProps</span></span>](sccountprops.md)
  
[<span data-ttu-id="84c28-141">ScDupPropset</span><span class="sxs-lookup"><span data-stu-id="84c28-141">ScDupPropset</span></span>](scduppropset.md)
  
[<span data-ttu-id="84c28-142">ScRelocNotifications</span><span class="sxs-lookup"><span data-stu-id="84c28-142">ScRelocNotifications</span></span>](screlocnotifications.md)

