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
ms.openlocfilehash: 3b5268f0b033126083a463f72e47c64957df07eb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577686"
---
# <a name="builddisplaytable"></a><span data-ttu-id="c272d-103">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="c272d-103">BuildDisplayTable</span></span>

  
  
<span data-ttu-id="c272d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c272d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c272d-105">创建一个或多个[DTPAGE](dtpage.md)结构中包含的属性页数据显示表。</span><span class="sxs-lookup"><span data-stu-id="c272d-105">Creates a display table from the property page data contained in one or more [DTPAGE](dtpage.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c272d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c272d-106">Header file:</span></span>  <br/> |<span data-ttu-id="c272d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="c272d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="c272d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c272d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c272d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c272d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c272d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="c272d-110">Called by:</span></span>  <br/> |<span data-ttu-id="c272d-111">服务提供商</span><span class="sxs-lookup"><span data-stu-id="c272d-111">Service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="c272d-112">参数</span><span class="sxs-lookup"><span data-stu-id="c272d-112">Parameters</span></span>

 <span data-ttu-id="c272d-113">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="c272d-113">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="c272d-114">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="c272d-114">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="c272d-115">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="c272d-115">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="c272d-116">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="c272d-116">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="c272d-117">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="c272d-117">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="c272d-118">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="c272d-118">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="c272d-119">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="c272d-119">_lpMalloc_</span></span>
  
> <span data-ttu-id="c272d-120">未使用;应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c272d-120">Unused; should be set to NULL.</span></span> 
    
 <span data-ttu-id="c272d-121">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="c272d-121">_hInstance_</span></span>
  
> <span data-ttu-id="c272d-122">[in]**BuildDisplayTable**从中检索资源 MAPI 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c272d-122">[in] An instance of a MAPI object from which **BuildDisplayTable** retrieves resources.</span></span> 
    
 <span data-ttu-id="c272d-123">_cPages_</span><span class="sxs-lookup"><span data-stu-id="c272d-123">_cPages_</span></span>
  
> <span data-ttu-id="c272d-124">[in]由_lpPage_参数指向[DTPAGE](dtpage.md)结构数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="c272d-124">[in] Count of [DTPAGE](dtpage.md) structures in the array pointed to by the  _lpPage_ parameter.</span></span> 
    
 <span data-ttu-id="c272d-125">_lpPage_</span><span class="sxs-lookup"><span data-stu-id="c272d-125">_lpPage_</span></span>
  
> <span data-ttu-id="c272d-126">[in]指针指向包含信息显示表页要生成的**DTPAGE**结构的数组。</span><span class="sxs-lookup"><span data-stu-id="c272d-126">[in] Pointer to an array of **DTPAGE** structures that contain information about the display table pages to be built.</span></span> 
    
 <span data-ttu-id="c272d-127">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c272d-127">_ulFlags_</span></span>
  
> <span data-ttu-id="c272d-128">[in]Flags 的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c272d-128">[in] Bitmask of flags.</span></span> <span data-ttu-id="c272d-129">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="c272d-129">The following flag can be set:</span></span>
    
<span data-ttu-id="c272d-130">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c272d-130">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c272d-131">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c272d-131">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="c272d-132">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c272d-132">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="c272d-133">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="c272d-133">_lppTable_</span></span>
  
> <span data-ttu-id="c272d-134">[输出]为显示表，该表公开[IMAPITable](imapitableiunknown.md)接口指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c272d-134">[out] Pointer to a pointer to the display table, which exposes the [IMAPITable](imapitableiunknown.md) interface.</span></span> 
    
 <span data-ttu-id="c272d-135">_lppTblData_</span><span class="sxs-lookup"><span data-stu-id="c272d-135">_lppTblData_</span></span>
  
> <span data-ttu-id="c272d-136">[传入、 传出]指向向 table 数据对象公开返回_lppTable_参数中的表上的[ITableData](itabledataiunknown.md)接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c272d-136">[in, out] Pointer to a pointer to a table data object exposing the [ITableData](itabledataiunknown.md) interface on the table returned in the  _lppTable_ parameter.</span></span> <span data-ttu-id="c272d-137">如果需要没有表数据对象，您应_lppTblData_的设置为 NULL 而不是一个指针值。</span><span class="sxs-lookup"><span data-stu-id="c272d-137">If no table data object is desired,  _lppTblData_ should be set to NULL instead of a pointer value.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c272d-138">返回值</span><span class="sxs-lookup"><span data-stu-id="c272d-138">Return value</span></span>

<span data-ttu-id="c272d-139">无</span><span class="sxs-lookup"><span data-stu-id="c272d-139">None</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c272d-140">注解</span><span class="sxs-lookup"><span data-stu-id="c272d-140">Remarks</span></span>

<span data-ttu-id="c272d-141">MAPI 使用所指的_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口时的功能如[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="c272d-141">MAPI uses the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c272d-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c272d-142">Notes to callers</span></span>

<span data-ttu-id="c272d-143">所有内容可能读取对话框资源，包括：</span><span class="sxs-lookup"><span data-stu-id="c272d-143">Everything possible is read from the dialog resource, including:</span></span>
  
- <span data-ttu-id="c272d-144">页面标题的、 读取资源中的对话框标题的[DTBLPAGE](dtblpage.md)结构的_ulbLpszLabel_成员。</span><span class="sxs-lookup"><span data-stu-id="c272d-144">The page title that is, the  _ulbLpszLabel_ member of the [DTBLPAGE](dtblpage.md) structure read from the dialog title in the resource.</span></span> 
    
- <span data-ttu-id="c272d-145">是的所有控件标题、 读取资源中的控件文本其他控制结构的_ulbLpszLabel_成员。</span><span class="sxs-lookup"><span data-stu-id="c272d-145">All control titles that is, the  _ulbLpszLabel_ members of other control structures read from the control text in the resource.</span></span> 
    
 <span data-ttu-id="c272d-146">**BuildDisplayTable**覆盖任何传递中与信息的输入的控件结构，从对话框资源，这意味着**BuildDisplayTable**的调用方动态无法指定页或控件的标题。</span><span class="sxs-lookup"><span data-stu-id="c272d-146">**BuildDisplayTable** overwrites anything passed in the input control structures with information from the dialog resource, which means the caller of **BuildDisplayTable** cannot dynamically specify page or control titles.</span></span> <span data-ttu-id="c272d-147">呼叫者需执行的操作可具有**BuildDisplayTable** _lppTableData_中返回的表数据对象，并更改中; 行或他们可以改为在表数据对象中手动构建显示表。</span><span class="sxs-lookup"><span data-stu-id="c272d-147">Callers who need to do that can have **BuildDisplayTable** return the table data object in  _lppTableData_ and change rows in it; or they can build the display table by hand in a table data object instead.</span></span> 
  
<span data-ttu-id="c272d-148">如果_lppTableData_未设置为 NULL，提供程序负责完成与显示表格释放的表数据对象。</span><span class="sxs-lookup"><span data-stu-id="c272d-148">If  _lppTableData_ is not set to NULL, the provider is responsible for freeing the table data object when it is finished with the display table.</span></span> 
  

