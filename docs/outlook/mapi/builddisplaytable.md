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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318093"
---
# <a name="builddisplaytable"></a><span data-ttu-id="b1f3e-103">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="b1f3e-103">BuildDisplayTable</span></span>

  
  
<span data-ttu-id="b1f3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1f3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1f3e-105">从包含在一个或多个[DTPAGE](dtpage.md)结构中的属性页数据创建显示表。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-105">Creates a display table from the property page data contained in one or more [DTPAGE](dtpage.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b1f3e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b1f3e-106">Header file:</span></span>  <br/> |<span data-ttu-id="b1f3e-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="b1f3e-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b1f3e-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="b1f3e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b1f3e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b1f3e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b1f3e-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="b1f3e-110">Called by:</span></span>  <br/> |<span data-ttu-id="b1f3e-111">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="b1f3e-111">Service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="b1f3e-112">参数</span><span class="sxs-lookup"><span data-stu-id="b1f3e-112">Parameters</span></span>

 <span data-ttu-id="b1f3e-113">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-113">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="b1f3e-114">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-114">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="b1f3e-115">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-115">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="b1f3e-116">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-116">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="b1f3e-117">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-117">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="b1f3e-118">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-118">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="b1f3e-119">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-119">_lpMalloc_</span></span>
  
> <span data-ttu-id="b1f3e-120">未经应设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-120">Unused; should be set to NULL.</span></span> 
    
 <span data-ttu-id="b1f3e-121">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-121">_hInstance_</span></span>
  
> <span data-ttu-id="b1f3e-122">实时**BuildDisplayTable**从中检索资源的 MAPI 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-122">[in] An instance of a MAPI object from which **BuildDisplayTable** retrieves resources.</span></span> 
    
 <span data-ttu-id="b1f3e-123">_cPages_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-123">_cPages_</span></span>
  
> <span data-ttu-id="b1f3e-124">实时由_lpPage_参数指向的数组中的[DTPAGE](dtpage.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-124">[in] Count of [DTPAGE](dtpage.md) structures in the array pointed to by the  _lpPage_ parameter.</span></span> 
    
 <span data-ttu-id="b1f3e-125">_lpPage_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-125">_lpPage_</span></span>
  
> <span data-ttu-id="b1f3e-126">实时指向**DTPAGE**结构数组的指针, 该数组包含要生成的显示表页的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-126">[in] Pointer to an array of **DTPAGE** structures that contain information about the display table pages to be built.</span></span> 
    
 <span data-ttu-id="b1f3e-127">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-127">_ulFlags_</span></span>
  
> <span data-ttu-id="b1f3e-128">实时标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-128">[in] Bitmask of flags.</span></span> <span data-ttu-id="b1f3e-129">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b1f3e-129">The following flag can be set:</span></span>
    
<span data-ttu-id="b1f3e-130">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b1f3e-130">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b1f3e-131">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-131">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="b1f3e-132">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-132">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="b1f3e-133">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-133">_lppTable_</span></span>
  
> <span data-ttu-id="b1f3e-134">排除指向显示[IMAPITable](imapitableiunknown.md)接口的显示表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-134">[out] Pointer to a pointer to the display table, which exposes the [IMAPITable](imapitableiunknown.md) interface.</span></span> 
    
 <span data-ttu-id="b1f3e-135">_lppTblData_</span><span class="sxs-lookup"><span data-stu-id="b1f3e-135">_lppTblData_</span></span>
  
> <span data-ttu-id="b1f3e-136">[in, out]指向指向表数据对象的指针的指针, 该对象公开在_lppTable_参数中返回的表上的[ITableData](itabledataiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-136">[in, out] Pointer to a pointer to a table data object exposing the [ITableData](itabledataiunknown.md) interface on the table returned in the  _lppTable_ parameter.</span></span> <span data-ttu-id="b1f3e-137">如果不需要表数据对象, 则应将_lppTblData_设置为 NULL, 而不是指针值。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-137">If no table data object is desired,  _lppTblData_ should be set to NULL instead of a pointer value.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b1f3e-138">返回值</span><span class="sxs-lookup"><span data-stu-id="b1f3e-138">Return value</span></span>

<span data-ttu-id="b1f3e-139">无</span><span class="sxs-lookup"><span data-stu-id="b1f3e-139">None</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b1f3e-140">注解</span><span class="sxs-lookup"><span data-stu-id="b1f3e-140">Remarks</span></span>

<span data-ttu-id="b1f3e-141">MAPI 将_lpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_指向的函数用于大多数内存分配和释放, 尤其是在调用对象接口时分配内存供客户端应用程序使用。例如[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-141">MAPI uses the functions pointed to by  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b1f3e-142">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b1f3e-142">Notes to callers</span></span>

<span data-ttu-id="b1f3e-143">可从对话框资源中读取所有可能的内容, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="b1f3e-143">Everything possible is read from the dialog resource, including:</span></span>
  
- <span data-ttu-id="b1f3e-144">页面标题即[DTBLPAGE](dtblpage.md)结构的_ulbLpszLabel_成员从该资源的对话框标题中读取。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-144">The page title that is, the  _ulbLpszLabel_ member of the [DTBLPAGE](dtblpage.md) structure read from the dialog title in the resource.</span></span> 
    
- <span data-ttu-id="b1f3e-145">所有控件标题即从资源中的控件文本读取的其他控件结构的_ulbLpszLabel_成员。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-145">All control titles that is, the  _ulbLpszLabel_ members of other control structures read from the control text in the resource.</span></span> 
    
 <span data-ttu-id="b1f3e-146">**BuildDisplayTable**将使用对话框资源中的信息覆盖输入控制结构中传递的任何内容, 这意味着**BuildDisplayTable**的调用方无法动态指定页面或控件标题。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-146">**BuildDisplayTable** overwrites anything passed in the input control structures with information from the dialog resource, which means the caller of **BuildDisplayTable** cannot dynamically specify page or control titles.</span></span> <span data-ttu-id="b1f3e-147">需要执行此操作的调用方可以让**BuildDisplayTable**返回_lppTableData_中的表数据对象并更改其中的行;也可以改为将显示表手动构建在表数据对象中。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-147">Callers who need to do that can have **BuildDisplayTable** return the table data object in  _lppTableData_ and change rows in it; or they can build the display table by hand in a table data object instead.</span></span> 
  
<span data-ttu-id="b1f3e-148">如果_lppTableData_未设置为 NULL, 则提供程序将负责在完成显示表后释放表数据对象。</span><span class="sxs-lookup"><span data-stu-id="b1f3e-148">If  _lppTableData_ is not set to NULL, the provider is responsible for freeing the table data object when it is finished with the display table.</span></span> 
  

