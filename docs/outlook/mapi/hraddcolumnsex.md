---
title: HrAddColumnsEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrAddColumnsEx
api_type:
- COM
ms.assetid: c0a65d2b-a9b8-4477-a1c7-18c8478126f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ca34fb2cce6e86c42e8e9525cd213f1008997d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348368"
---
# <a name="hraddcolumnsex"></a><span data-ttu-id="38e9c-103">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="38e9c-103">HrAddColumnsEx</span></span>

  
  
<span data-ttu-id="38e9c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38e9c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38e9c-105">将列添加或移动到现有表的开头。</span><span class="sxs-lookup"><span data-stu-id="38e9c-105">Adds or moves columns to the beginning of an existing table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38e9c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="38e9c-106">Header file:</span></span>  <br/> |<span data-ttu-id="38e9c-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="38e9c-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="38e9c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="38e9c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="38e9c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="38e9c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="38e9c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="38e9c-110">Called by:</span></span>  <br/> |<span data-ttu-id="38e9c-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="38e9c-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrAddColumnsEx(
  LPMAPITABLE lptbl,
  LPSPropTagArray lpproptagColumnsNew,
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  void (FAR * lpfnFilterColumns)(
  LPSPropTagArray ptaga)
);
```

## <a name="parameters"></a><span data-ttu-id="38e9c-112">参数</span><span class="sxs-lookup"><span data-stu-id="38e9c-112">Parameters</span></span>

 <span data-ttu-id="38e9c-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="38e9c-113">_lptbl_</span></span>
  
> <span data-ttu-id="38e9c-114">实时指向受影响的 MAPI 表的指针。</span><span class="sxs-lookup"><span data-stu-id="38e9c-114">[in] Pointer to the MAPI table affected.</span></span> 
    
 <span data-ttu-id="38e9c-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="38e9c-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="38e9c-116">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含要添加或移动到表开头的属性的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="38e9c-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="38e9c-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="38e9c-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="38e9c-118">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="38e9c-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="38e9c-119">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="38e9c-119">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="38e9c-120">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="38e9c-120">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="38e9c-121">_lpfnFilterColumns_</span><span class="sxs-lookup"><span data-stu-id="38e9c-121">_lpfnFilterColumns_</span></span>
  
> <span data-ttu-id="38e9c-122">实时指向由调用方提供的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="38e9c-122">[in] Pointer to a callback function furnished by the caller.</span></span> <span data-ttu-id="38e9c-123">如果将_lpfnFilterColumns_参数设置为 NULL, 则不会进行任何回调。</span><span class="sxs-lookup"><span data-stu-id="38e9c-123">If the  _lpfnFilterColumns_ parameter is set to NULL, no callback is made.</span></span> 
    
 <span data-ttu-id="38e9c-124">_ptaga_</span><span class="sxs-lookup"><span data-stu-id="38e9c-124">_ptaga_</span></span>
  
> <span data-ttu-id="38e9c-125">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含在添加属性或将属性移到开头之前表中已存在的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="38e9c-125">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains the array of property tags already existing in the table before properties are added or moved to the beginning.</span></span> <span data-ttu-id="38e9c-126">**HrAddColumnsEx**将此指针作为参数传递给由_lpfnFilterColumns_指向的回调函数。</span><span class="sxs-lookup"><span data-stu-id="38e9c-126">**HrAddColumnsEx** passes this pointer as the parameter to the callback function pointed to by  _lpfnFilterColumns_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38e9c-127">返回值</span><span class="sxs-lookup"><span data-stu-id="38e9c-127">Return value</span></span>

<span data-ttu-id="38e9c-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="38e9c-128">S_OK</span></span> 
  
> <span data-ttu-id="38e9c-129">调用成功, 并已移动或添加指定的列。</span><span class="sxs-lookup"><span data-stu-id="38e9c-129">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="38e9c-130">注解</span><span class="sxs-lookup"><span data-stu-id="38e9c-130">Remarks</span></span>

<span data-ttu-id="38e9c-131">使用_lpproptagColumnsNew_参数传递给**HrAddColumnsEx**的属性成为对[IMAPITable:: QueryRows](imapitable-queryrows.md)方法的后续调用中公开的第一个属性。</span><span class="sxs-lookup"><span data-stu-id="38e9c-131">The properties passed to **HrAddColumnsEx** using the  _lpproptagColumnsNew_ parameter become the first properties exposed on subsequent calls to the [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> <span data-ttu-id="38e9c-132">在表中先前未在_lpproptagColumnsNew_参数中指定的任何属性都将在所有添加和移动的属性之后公开。</span><span class="sxs-lookup"><span data-stu-id="38e9c-132">Any properties previously in the table that were not specified in the  _lpproptagColumnsNew_ parameter are exposed after all the added and moved properties.</span></span> 
  
<span data-ttu-id="38e9c-133">如果在调用**QueryRows**时未定义任何表属性, 则将使用属性类型 PT_NULL 和属性标识符 PROP_ID_NULL 返回它们。</span><span class="sxs-lookup"><span data-stu-id="38e9c-133">If any table properties are undefined when **QueryRows** is called, they are returned with property type PT_NULL and property identifier PROP_ID_NULL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="38e9c-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="38e9c-134">Notes to callers</span></span>

<span data-ttu-id="38e9c-135">**HrAddColumnsEx**函数允许调用方提供一个回调函数, 以筛选表中已存在的列, 例如, 将字符串从属性类型 PT_UNICODE 转换为 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="38e9c-135">The **HrAddColumnsEx** function allows the caller to furnish a callback function to filter the columns that were already in the table, for example to convert strings from property type PT_UNICODE to PT_STRING8.</span></span> <span data-ttu-id="38e9c-136">**HrAddColumnsEx**将一个指针传递给之前的现有列, 并将其设置为回调函数的参数。</span><span class="sxs-lookup"><span data-stu-id="38e9c-136">**HrAddColumnsEx** passes a pointer to the previously existing column set as the parameter to the callback function.</span></span> <span data-ttu-id="38e9c-137">回调函数可以更改属性标记数组中的数据, 但不能添加新标记。</span><span class="sxs-lookup"><span data-stu-id="38e9c-137">The callback function can change data in the property tag array but cannot add new tags.</span></span> 
  
 <span data-ttu-id="38e9c-138">**HrAddColumnsEx**首先调用回调函数 (如果提供了一个), 然后添加或移动指定的列, 最后调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)。</span><span class="sxs-lookup"><span data-stu-id="38e9c-138">**HrAddColumnsEx** first calls the callback function if one is furnished, then adds or moves the specified columns, and finally calls [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span> 
  
<span data-ttu-id="38e9c-139">_lpAllocateBuffer_和_lpFreeBuffer_输入参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="38e9c-139">The  _lpAllocateBuffer_ and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="38e9c-140">传递给**HrAddColumnsEx**的指针的确切值取决于调用方是客户端应用程序还是服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="38e9c-140">The exact values of the pointers passed to **HrAddColumnsEx** depend on whether the caller is a client application or a service provider.</span></span> <span data-ttu-id="38e9c-141">客户端将指向 MAPI 函数的指针传递给指定的名称。</span><span class="sxs-lookup"><span data-stu-id="38e9c-141">A client passes pointers to the MAPI functions with the specified names.</span></span> <span data-ttu-id="38e9c-142">服务提供程序在其初始化调用中传递接收到的指针, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法来检索它们。</span><span class="sxs-lookup"><span data-stu-id="38e9c-142">A service provider passes the pointers it received in its initialization call or retrieved by calling the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="38e9c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38e9c-143">See also</span></span>



[<span data-ttu-id="38e9c-144">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="38e9c-144">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)

