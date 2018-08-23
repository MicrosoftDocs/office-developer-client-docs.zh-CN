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
ms.openlocfilehash: 566a9d23c46ec717eb5eed711fff801b15d49fc1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564232"
---
# <a name="hraddcolumnsex"></a><span data-ttu-id="77b1a-103">HrAddColumnsEx</span><span class="sxs-lookup"><span data-stu-id="77b1a-103">HrAddColumnsEx</span></span>

  
  
<span data-ttu-id="77b1a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77b1a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77b1a-105">添加或移到现有表的起点的列。</span><span class="sxs-lookup"><span data-stu-id="77b1a-105">Adds or moves columns to the beginning of an existing table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="77b1a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="77b1a-106">Header file:</span></span>  <br/> |<span data-ttu-id="77b1a-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="77b1a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="77b1a-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="77b1a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="77b1a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="77b1a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="77b1a-110">调用：</span><span class="sxs-lookup"><span data-stu-id="77b1a-110">Called by:</span></span>  <br/> |<span data-ttu-id="77b1a-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="77b1a-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="77b1a-112">参数</span><span class="sxs-lookup"><span data-stu-id="77b1a-112">Parameters</span></span>

 <span data-ttu-id="77b1a-113">_lptbl_</span><span class="sxs-lookup"><span data-stu-id="77b1a-113">_lptbl_</span></span>
  
> <span data-ttu-id="77b1a-114">[in]指向受影响的 MAPI 表。</span><span class="sxs-lookup"><span data-stu-id="77b1a-114">[in] Pointer to the MAPI table affected.</span></span> 
    
 <span data-ttu-id="77b1a-115">_lpproptagColumnsNew_</span><span class="sxs-lookup"><span data-stu-id="77b1a-115">_lpproptagColumnsNew_</span></span>
  
> <span data-ttu-id="77b1a-116">[in]指向[SPropTagArray](sproptagarray.md)结构，其中包含要添加或移至表格的开头的属性的属性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="77b1a-116">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags for the properties to be added or moved to the beginning of the table.</span></span> 
    
 <span data-ttu-id="77b1a-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="77b1a-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="77b1a-118">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="77b1a-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="77b1a-119">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="77b1a-119">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="77b1a-120">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="77b1a-120">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="77b1a-121">_lpfnFilterColumns_</span><span class="sxs-lookup"><span data-stu-id="77b1a-121">_lpfnFilterColumns_</span></span>
  
> <span data-ttu-id="77b1a-122">[in]指向提供呼叫者的回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="77b1a-122">[in] Pointer to a callback function furnished by the caller.</span></span> <span data-ttu-id="77b1a-123">如果_lpfnFilterColumns_参数设置为 NULL，则进行不回拨。</span><span class="sxs-lookup"><span data-stu-id="77b1a-123">If the  _lpfnFilterColumns_ parameter is set to NULL, no callback is made.</span></span> 
    
 <span data-ttu-id="77b1a-124">_ptaga_</span><span class="sxs-lookup"><span data-stu-id="77b1a-124">_ptaga_</span></span>
  
> <span data-ttu-id="77b1a-125">[in]指向包含属性标记之前添加或移至开头属性表中已存在数组[SPropTagArray](sproptagarray.md)结构。</span><span class="sxs-lookup"><span data-stu-id="77b1a-125">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains the array of property tags already existing in the table before properties are added or moved to the beginning.</span></span> <span data-ttu-id="77b1a-126">**HrAddColumnsEx**传递给回调函数的参数为此指针指向_lpfnFilterColumns_。</span><span class="sxs-lookup"><span data-stu-id="77b1a-126">**HrAddColumnsEx** passes this pointer as the parameter to the callback function pointed to by  _lpfnFilterColumns_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="77b1a-127">返回值</span><span class="sxs-lookup"><span data-stu-id="77b1a-127">Return value</span></span>

<span data-ttu-id="77b1a-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="77b1a-128">S_OK</span></span> 
  
> <span data-ttu-id="77b1a-129">调用成功，并指定的列已移动或添加。</span><span class="sxs-lookup"><span data-stu-id="77b1a-129">The call succeeded and the specified columns were moved or added.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="77b1a-130">注解</span><span class="sxs-lookup"><span data-stu-id="77b1a-130">Remarks</span></span>

<span data-ttu-id="77b1a-131">传递给**HrAddColumnsEx**使用_lpproptagColumnsNew_参数的属性将成为公开上后续调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法的第一个属性。</span><span class="sxs-lookup"><span data-stu-id="77b1a-131">The properties passed to **HrAddColumnsEx** using the  _lpproptagColumnsNew_ parameter become the first properties exposed on subsequent calls to the [IMAPITable::QueryRows](imapitable-queryrows.md) method.</span></span> <span data-ttu-id="77b1a-132">前面的表的_lpproptagColumnsNew_参数中未指定任何属性公开后的添加和移动的所有属性。</span><span class="sxs-lookup"><span data-stu-id="77b1a-132">Any properties previously in the table that were not specified in the  _lpproptagColumnsNew_ parameter are exposed after all the added and moved properties.</span></span> 
  
<span data-ttu-id="77b1a-133">如果调用**QueryRows**时未定义任何表属性，也会返回与属性类型 PT_NULL 属性标识符 PROP_ID_NULL。</span><span class="sxs-lookup"><span data-stu-id="77b1a-133">If any table properties are undefined when **QueryRows** is called, they are returned with property type PT_NULL and property identifier PROP_ID_NULL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="77b1a-134">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="77b1a-134">Notes to callers</span></span>

<span data-ttu-id="77b1a-135">**HrAddColumnsEx**函数允许呼叫者提供了一个回调函数来筛选表中，例如将字符串转换为 PT_STRING8 属性类型 PT_UNICODE 中已存在的列。</span><span class="sxs-lookup"><span data-stu-id="77b1a-135">The **HrAddColumnsEx** function allows the caller to furnish a callback function to filter the columns that were already in the table, for example to convert strings from property type PT_UNICODE to PT_STRING8.</span></span> <span data-ttu-id="77b1a-136">**HrAddColumnsEx**将指针传递到以前的现有列将作为参数设置为的回调函数中。</span><span class="sxs-lookup"><span data-stu-id="77b1a-136">**HrAddColumnsEx** passes a pointer to the previously existing column set as the parameter to the callback function.</span></span> <span data-ttu-id="77b1a-137">回调函数可以更改属性标记数组中的数据，但不能添加新的标签。</span><span class="sxs-lookup"><span data-stu-id="77b1a-137">The callback function can change data in the property tag array but cannot add new tags.</span></span> 
  
 <span data-ttu-id="77b1a-138">如果一个提供，然后添加或移动指定的列，并且最后调用[IMAPITable::SetColumns](imapitable-setcolumns.md)， **HrAddColumnsEx**首先调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="77b1a-138">**HrAddColumnsEx** first calls the callback function if one is furnished, then adds or moves the specified columns, and finally calls [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span> 
  
<span data-ttu-id="77b1a-139">_LpAllocateBuffer_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="77b1a-139">The  _lpAllocateBuffer_ and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="77b1a-140">传递给**HrAddColumnsEx**的指针的确切值取决于呼叫者是否位于客户端应用程序或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="77b1a-140">The exact values of the pointers passed to **HrAddColumnsEx** depend on whether the caller is a client application or a service provider.</span></span> <span data-ttu-id="77b1a-141">客户端将指针传递到具有指定名称的 MAPI 功能。</span><span class="sxs-lookup"><span data-stu-id="77b1a-141">A client passes pointers to the MAPI functions with the specified names.</span></span> <span data-ttu-id="77b1a-142">服务提供商将传递它在其初始化呼叫中收到或通过调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索的指针。</span><span class="sxs-lookup"><span data-stu-id="77b1a-142">A service provider passes the pointers it received in its initialization call or retrieved by calling the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77b1a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77b1a-143">See also</span></span>



[<span data-ttu-id="77b1a-144">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="77b1a-144">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)

