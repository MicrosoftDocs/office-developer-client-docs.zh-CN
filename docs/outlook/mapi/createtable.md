---
title: CreateTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CreateTable
api_type:
- HeaderDef
ms.assetid: 106ce3d8-d0bf-4a0e-9a15-dc8988d0eb58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8c399569e68b8cb55d803733ed93105ea0be799
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435010"
---
# <a name="createtable"></a><span data-ttu-id="b4327-103">CreateTable</span><span class="sxs-lookup"><span data-stu-id="b4327-103">CreateTable</span></span>

  
  
<span data-ttu-id="b4327-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4327-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4327-105">创建可用于创建表内容的 [ITableData](itabledataiunknown.md) 对象的结构和对象句柄。</span><span class="sxs-lookup"><span data-stu-id="b4327-105">Creates structures and an object handle for an [ITableData](itabledataiunknown.md) object which can be used to create table contents.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b4327-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b4327-106">Header file:</span></span>  <br/> |<span data-ttu-id="b4327-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="b4327-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b4327-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="b4327-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b4327-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b4327-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b4327-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="b4327-110">Called by:</span></span>  <br/> |<span data-ttu-id="b4327-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b4327-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE CreateTable(
  LPCIID lpInterface,
  ALLOCATEBUFFER FAR * lpAllocateBuffer,
  ALLOCATEMORE FAR * lpAllocateMore,
  FREEBUFFER FAR * lpFreeBuffer,
  LPVOID lpvReserved,
  ULONG ulTableType,
  ULONG ulPropTagIndexColumn,
  LPSPropTagArray lpSPropTagArrayColumns,
  LPTABLEDATA FAR * lppTableData
);
```

## <a name="parameters"></a><span data-ttu-id="b4327-112">参数</span><span class="sxs-lookup"><span data-stu-id="b4327-112">Parameters</span></span>

 <span data-ttu-id="b4327-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="b4327-113">_lpInterface_</span></span>
  
> <span data-ttu-id="b4327-114">[in]指向表数据 (IID) 接口标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b4327-114">[in] Pointer to an interface identifier (IID) for the table data object.</span></span> <span data-ttu-id="b4327-115">有效的接口标识符IID_IMAPITableData。</span><span class="sxs-lookup"><span data-stu-id="b4327-115">The valid interface identifier is IID_IMAPITableData.</span></span> <span data-ttu-id="b4327-116">在  _lpInterface_ 参数中传递 NULL 还会导致  _lppTableData_ 参数中返回的表数据对象被强制转换到表数据对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="b4327-116">Passing NULL in the  _lpInterface_ parameter also causes the table data object returned in the  _lppTableData_ parameter to be cast to the standard interface for a table data object.</span></span> 
    
 <span data-ttu-id="b4327-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="b4327-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="b4327-118">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="b4327-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="b4327-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="b4327-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="b4327-120">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="b4327-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="b4327-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="b4327-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="b4327-122">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="b4327-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="b4327-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="b4327-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="b4327-124">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="b4327-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="b4327-125">_ulTableType_</span><span class="sxs-lookup"><span data-stu-id="b4327-125">_ulTableType_</span></span>
  
> <span data-ttu-id="b4327-126">[in]作为 [IMAPITable：：GetStatus](imapitable-getstatus.md) 的一部分提供给客户端应用程序或服务提供商的表类型在其表视图上返回数据。</span><span class="sxs-lookup"><span data-stu-id="b4327-126">[in] A table type that is available to a client application or service provider as part of the [IMAPITable::GetStatus](imapitable-getstatus.md) return data on its table views.</span></span> <span data-ttu-id="b4327-127">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="b4327-127">Possible values are:</span></span> 
    
<span data-ttu-id="b4327-128">TBLTYPE_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="b4327-128">TBLTYPE_DYNAMIC</span></span> 
  
> <span data-ttu-id="b4327-129">该表的内容是动态的，并且可能会随着基础数据的变化而更改。</span><span class="sxs-lookup"><span data-stu-id="b4327-129">The table's contents are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="b4327-130">TBLTYPE_KEYSET</span><span class="sxs-lookup"><span data-stu-id="b4327-130">TBLTYPE_KEYSET</span></span> 
  
> <span data-ttu-id="b4327-131">表中的行是固定的，但这些行中的值是动态的，并且可能会随着基础数据的变化而更改。</span><span class="sxs-lookup"><span data-stu-id="b4327-131">The rows in the table are fixed, but the values in these rows are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="b4327-132">TBLTYPE_SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="b4327-132">TBLTYPE_SNAPSHOT</span></span> 
  
> <span data-ttu-id="b4327-133">该表是静态表，在基础数据更改时不会更改内容。</span><span class="sxs-lookup"><span data-stu-id="b4327-133">The table is static and the contents do not change when the underlying data changes.</span></span> 
    
 <span data-ttu-id="b4327-134">_ulPropTagIndexColumn_</span><span class="sxs-lookup"><span data-stu-id="b4327-134">_ulPropTagIndexColumn_</span></span>
  
> <span data-ttu-id="b4327-135">[in]更改表数据时使用的列的索引号。</span><span class="sxs-lookup"><span data-stu-id="b4327-135">[in] Index number of the column for use when changing table data.</span></span> 
    
 <span data-ttu-id="b4327-136">_lpSPropTagArrayColumns_</span><span class="sxs-lookup"><span data-stu-id="b4327-136">_lpSPropTagArrayColumns_</span></span>
  
> <span data-ttu-id="b4327-137">[in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含一组属性标记，指示对象保存数据的表中所需的属性。</span><span class="sxs-lookup"><span data-stu-id="b4327-137">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating the properties required in the table for which the object holds data.</span></span> 
    
 <span data-ttu-id="b4327-138">_lppTableData_</span><span class="sxs-lookup"><span data-stu-id="b4327-138">_lppTableData_</span></span>
  
> <span data-ttu-id="b4327-139">[out]指向返回的表数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b4327-139">[out] Pointer to a pointer to the returned table data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b4327-140">返回值</span><span class="sxs-lookup"><span data-stu-id="b4327-140">Return value</span></span>

<span data-ttu-id="b4327-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4327-141">S_OK</span></span> 
  
> <span data-ttu-id="b4327-142">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="b4327-142">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b4327-143">备注</span><span class="sxs-lookup"><span data-stu-id="b4327-143">Remarks</span></span>

<span data-ttu-id="b4327-144">_lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 输入参数分别指向 [MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数。  [](mapiallocatemore.md)</span><span class="sxs-lookup"><span data-stu-id="b4327-144">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="b4327-145">调用 **CreateTable** 的客户端应用程序将传递指向刚命名的 MAPI 函数的指针;服务提供商将指针传递给其在其初始化调用中收到的或通过调用 [IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md) 方法检索的函数。</span><span class="sxs-lookup"><span data-stu-id="b4327-145">A client application calling **CreateTable** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions that it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b4327-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4327-146">See also</span></span>



[<span data-ttu-id="b4327-147">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b4327-147">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

