---
title: BuildDisplayTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- BuildDisplayTable
api_type:
- HeaderDef
ms.assetid: 0846415b-6fe1-4504-8620-108af6719015
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c5e6078be05ff846b7737ff53e9a6338fcb2141
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431594"
---
# <a name="builddisplaytable"></a><span data-ttu-id="2ec74-103">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="2ec74-103">BuildDisplayTable</span></span>

  
  
<span data-ttu-id="2ec74-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ec74-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ec74-105">根据一个或多个 [DTPAGE](dtpage.md) 结构中包含的属性页数据创建显示表。</span><span class="sxs-lookup"><span data-stu-id="2ec74-105">Creates a display table from the property page data contained in one or more [DTPAGE](dtpage.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2ec74-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2ec74-106">Header file:</span></span>  <br/> |<span data-ttu-id="2ec74-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="2ec74-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="2ec74-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="2ec74-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2ec74-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2ec74-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2ec74-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="2ec74-110">Called by:</span></span>  <br/> |<span data-ttu-id="2ec74-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2ec74-111">Service providers</span></span>  <br/> |
   
```cpp
STDAPI BuildDisplayTable(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPALLOCATEMORE lpAllocateMore,
  LPFREEBUFFER lpFreeBuffer,
  LPMALLOC lpMalloc,
  HINSTANCE hInstance,
  UINT cPages,
  LPDTPAGE lpPage,
  ULONG ulFlags,
  LPMAPITABLE * lppTable,
  LPTABLEDATA * lppTblData
);
```

## <a name="parameters"></a><span data-ttu-id="2ec74-112">参数</span><span class="sxs-lookup"><span data-stu-id="2ec74-112">Parameters</span></span>

 <span data-ttu-id="2ec74-113">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="2ec74-113">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="2ec74-114">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="2ec74-114">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="2ec74-115">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="2ec74-115">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="2ec74-116">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="2ec74-116">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="2ec74-117">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="2ec74-117">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="2ec74-118">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="2ec74-118">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="2ec74-119">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="2ec74-119">_lpMalloc_</span></span>
  
> <span data-ttu-id="2ec74-120">未使用;应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ec74-120">Unused; should be set to NULL.</span></span> 
    
 <span data-ttu-id="2ec74-121">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="2ec74-121">_hInstance_</span></span>
  
> <span data-ttu-id="2ec74-122">[in] **BuildDisplayTable** 从中检索资源的 MAPI 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="2ec74-122">[in] An instance of a MAPI object from which **BuildDisplayTable** retrieves resources.</span></span> 
    
 <span data-ttu-id="2ec74-123">_cPages_</span><span class="sxs-lookup"><span data-stu-id="2ec74-123">_cPages_</span></span>
  
> <span data-ttu-id="2ec74-124">[in]_lpPage_ 参数指向的数组中的 [DTPAGE](dtpage.md)结构计数。</span><span class="sxs-lookup"><span data-stu-id="2ec74-124">[in] Count of [DTPAGE](dtpage.md) structures in the array pointed to by the  _lpPage_ parameter.</span></span> 
    
 <span data-ttu-id="2ec74-125">_lpPage_</span><span class="sxs-lookup"><span data-stu-id="2ec74-125">_lpPage_</span></span>
  
> <span data-ttu-id="2ec74-126">[in]指向包含有关要构建的显示表页的信息的 **DTPAGE** 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="2ec74-126">[in] Pointer to an array of **DTPAGE** structures that contain information about the display table pages to be built.</span></span> 
    
 <span data-ttu-id="2ec74-127">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2ec74-127">_ulFlags_</span></span>
  
> <span data-ttu-id="2ec74-128">[in]标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2ec74-128">[in] Bitmask of flags.</span></span> <span data-ttu-id="2ec74-129">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2ec74-129">The following flag can be set:</span></span>
    
<span data-ttu-id="2ec74-130">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2ec74-130">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2ec74-131">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="2ec74-131">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="2ec74-132">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2ec74-132">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="2ec74-133">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="2ec74-133">_lppTable_</span></span>
  
> <span data-ttu-id="2ec74-134">[out]指向显示表的指针的指针，显示表公开 [IMAPITable](imapitableiunknown.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="2ec74-134">[out] Pointer to a pointer to the display table, which exposes the [IMAPITable](imapitableiunknown.md) interface.</span></span> 
    
 <span data-ttu-id="2ec74-135">_lppTblData_</span><span class="sxs-lookup"><span data-stu-id="2ec74-135">_lppTblData_</span></span>
  
> <span data-ttu-id="2ec74-136">[in， out]指向在 _lppTable_ 参数中返回的表上公开 [ITableData](itabledataiunknown.md)接口的表数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2ec74-136">[in, out] Pointer to a pointer to a table data object exposing the [ITableData](itabledataiunknown.md) interface on the table returned in the  _lppTable_ parameter.</span></span> <span data-ttu-id="2ec74-137">如果不需要表数据对象，则  _lppTblData_ 应设置为 NULL，而不是指针值。</span><span class="sxs-lookup"><span data-stu-id="2ec74-137">If no table data object is desired,  _lppTblData_ should be set to NULL instead of a pointer value.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2ec74-138">返回值</span><span class="sxs-lookup"><span data-stu-id="2ec74-138">Return value</span></span>

<span data-ttu-id="2ec74-139">无</span><span class="sxs-lookup"><span data-stu-id="2ec74-139">None</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2ec74-140">备注</span><span class="sxs-lookup"><span data-stu-id="2ec74-140">Remarks</span></span>

<span data-ttu-id="2ec74-141">MAPI 使用 _lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 指向的函数进行大多数内存分配和处理，尤其是当调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)和 [IMAPITable：：QueryRows](imapitable-queryrows.md)等对象接口时，分配供客户端应用程序使用的内存。 </span><span class="sxs-lookup"><span data-stu-id="2ec74-141">MAPI uses the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2ec74-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2ec74-142">Notes to callers</span></span>

<span data-ttu-id="2ec74-143">所有可能内容都从对话框资源中读取，包括：</span><span class="sxs-lookup"><span data-stu-id="2ec74-143">Everything possible is read from the dialog resource, including:</span></span>
  
- <span data-ttu-id="2ec74-144">页面标题，即从资源中的对话框标题读取 [的 DTBLPAGE](dtblpage.md)结构的 _ulbLpszLabel_ 成员。</span><span class="sxs-lookup"><span data-stu-id="2ec74-144">The page title that is, the  _ulbLpszLabel_ member of the [DTBLPAGE](dtblpage.md) structure read from the dialog title in the resource.</span></span> 
    
- <span data-ttu-id="2ec74-145">所有控件标题，即其他控件结构的  _ulbLpszLabel_ 成员，从资源中的控件文本读取。</span><span class="sxs-lookup"><span data-stu-id="2ec74-145">All control titles that is, the  _ulbLpszLabel_ members of other control structures read from the control text in the resource.</span></span> 
    
 <span data-ttu-id="2ec74-146">**BuildDisplayTable** 使用对话框资源的信息覆盖输入控件结构中传递的任何内容，这意味着 **BuildDisplayTable** 的调用方无法动态指定页面或控件标题。</span><span class="sxs-lookup"><span data-stu-id="2ec74-146">**BuildDisplayTable** overwrites anything passed in the input control structures with information from the dialog resource, which means the caller of **BuildDisplayTable** cannot dynamically specify page or control titles.</span></span> <span data-ttu-id="2ec74-147">需要让 **BuildDisplayTable** 这样做的调用方在  _lppTableData_ 中返回表数据对象并更改其行;或者他们可以在表数据对象中手动生成显示表。</span><span class="sxs-lookup"><span data-stu-id="2ec74-147">Callers who need to do that can have **BuildDisplayTable** return the table data object in  _lppTableData_ and change rows in it; or they can build the display table by hand in a table data object instead.</span></span> 
  
<span data-ttu-id="2ec74-148">如果  _lppTableData_ 未设置为 NULL，则提供程序负责在表数据对象处理完显示表后释放该对象。</span><span class="sxs-lookup"><span data-stu-id="2ec74-148">If  _lppTableData_ is not set to NULL, the provider is responsible for freeing the table data object when it is finished with the display table.</span></span> 
  

