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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332982"
---
# <a name="createtable"></a><span data-ttu-id="f0ea1-103">CreateTable</span><span class="sxs-lookup"><span data-stu-id="f0ea1-103">CreateTable</span></span>

  
  
<span data-ttu-id="f0ea1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0ea1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0ea1-105">为[ITableData](itabledataiunknown.md)对象创建结构和对象句柄, 该对象可用于创建表格内容。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-105">Creates structures and an object handle for an [ITableData](itabledataiunknown.md) object which can be used to create table contents.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f0ea1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f0ea1-106">Header file:</span></span>  <br/> |<span data-ttu-id="f0ea1-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="f0ea1-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f0ea1-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f0ea1-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f0ea1-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f0ea1-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f0ea1-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f0ea1-110">Called by:</span></span>  <br/> |<span data-ttu-id="f0ea1-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f0ea1-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="f0ea1-112">参数</span><span class="sxs-lookup"><span data-stu-id="f0ea1-112">Parameters</span></span>

 <span data-ttu-id="f0ea1-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-113">_lpInterface_</span></span>
  
> <span data-ttu-id="f0ea1-114">实时指向 table 数据对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-114">[in] Pointer to an interface identifier (IID) for the table data object.</span></span> <span data-ttu-id="f0ea1-115">有效的接口标识符为 IID_IMAPITableData。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-115">The valid interface identifier is IID_IMAPITableData.</span></span> <span data-ttu-id="f0ea1-116">在_lpInterface_参数中传递 NULL 还会导致在_lppTableData_参数中返回的表数据对象将转换为 table 数据对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-116">Passing NULL in the  _lpInterface_ parameter also causes the table data object returned in the  _lppTableData_ parameter to be cast to the standard interface for a table data object.</span></span> 
    
 <span data-ttu-id="f0ea1-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="f0ea1-118">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="f0ea1-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="f0ea1-120">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="f0ea1-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="f0ea1-122">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="f0ea1-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="f0ea1-124">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="f0ea1-125">_ulTableType_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-125">_ulTableType_</span></span>
  
> <span data-ttu-id="f0ea1-126">实时作为[IMAPITable:: GetStatus](imapitable-getstatus.md)的一部分提供给客户端应用程序或服务提供程序的表类型将返回其表视图中的数据。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-126">[in] A table type that is available to a client application or service provider as part of the [IMAPITable::GetStatus](imapitable-getstatus.md) return data on its table views.</span></span> <span data-ttu-id="f0ea1-127">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="f0ea1-127">Possible values are:</span></span> 
    
<span data-ttu-id="f0ea1-128">TBLTYPE_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="f0ea1-128">TBLTYPE_DYNAMIC</span></span> 
  
> <span data-ttu-id="f0ea1-129">表的内容是动态的, 并且可以随着基础数据的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-129">The table's contents are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="f0ea1-130">TBLTYPE_KEYSET</span><span class="sxs-lookup"><span data-stu-id="f0ea1-130">TBLTYPE_KEYSET</span></span> 
  
> <span data-ttu-id="f0ea1-131">表中的行是固定的, 但这些行中的值是动态的, 并且可以随着基础数据的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-131">The rows in the table are fixed, but the values in these rows are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="f0ea1-132">TBLTYPE_SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="f0ea1-132">TBLTYPE_SNAPSHOT</span></span> 
  
> <span data-ttu-id="f0ea1-133">该表是静态的, 并且在基础数据发生更改时内容不会更改。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-133">The table is static and the contents do not change when the underlying data changes.</span></span> 
    
 <span data-ttu-id="f0ea1-134">_ulPropTagIndexColumn_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-134">_ulPropTagIndexColumn_</span></span>
  
> <span data-ttu-id="f0ea1-135">实时更改表数据时使用的列的索引号。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-135">[in] Index number of the column for use when changing table data.</span></span> 
    
 <span data-ttu-id="f0ea1-136">_lpSPropTagArrayColumns_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-136">_lpSPropTagArrayColumns_</span></span>
  
> <span data-ttu-id="f0ea1-137">实时指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个由属性标记数组组成的数组, 这些标记指明了对象为其保留数据的表中所需的属性。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-137">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating the properties required in the table for which the object holds data.</span></span> 
    
 <span data-ttu-id="f0ea1-138">_lppTableData_</span><span class="sxs-lookup"><span data-stu-id="f0ea1-138">_lppTableData_</span></span>
  
> <span data-ttu-id="f0ea1-139">排除指向返回的 table 数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-139">[out] Pointer to a pointer to the returned table data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f0ea1-140">返回值</span><span class="sxs-lookup"><span data-stu-id="f0ea1-140">Return value</span></span>

<span data-ttu-id="f0ea1-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0ea1-141">S_OK</span></span> 
  
> <span data-ttu-id="f0ea1-142">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-142">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f0ea1-143">注解</span><span class="sxs-lookup"><span data-stu-id="f0ea1-143">Remarks</span></span>

<span data-ttu-id="f0ea1-144">" _lpAllocateBuffer_"、" _lpAllocateMore_" 和 " _lpFreeBuffer_ " 输入参数分别指向 " [MAPIAllocateBuffer](mapiallocatebuffer.md)"、" [MAPIAllocateMore](mapiallocatemore.md)" 和 " [MAPIFreeBuffer](mapifreebuffer.md) " 函数。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-144">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="f0ea1-145">调用**CreateTable**的客户端应用程序传递到刚刚命名的 MAPI 函数的指针。服务提供程序将指向其初始化调用中收到的这些函数的指针传递给这些函数, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。</span><span class="sxs-lookup"><span data-stu-id="f0ea1-145">A client application calling **CreateTable** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions that it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f0ea1-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0ea1-146">See also</span></span>



[<span data-ttu-id="f0ea1-147">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f0ea1-147">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

