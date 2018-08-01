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
ms.openlocfilehash: 5f42e1eb0d120d2fbb785e63b451acdd2d5a91f1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774743"
---
# <a name="createtable"></a><span data-ttu-id="f5d2d-103">CreateTable</span><span class="sxs-lookup"><span data-stu-id="f5d2d-103">CreateTable</span></span>

  
  
<span data-ttu-id="f5d2d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f5d2d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f5d2d-105">创建结构和[ITableData](itabledataiunknown.md)对象可用于创建目录对象句柄。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-105">Creates structures and an object handle for an [ITableData](itabledataiunknown.md) object which can be used to create table contents.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5d2d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f5d2d-106">Header file:</span></span>  <br/> |<span data-ttu-id="f5d2d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="f5d2d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f5d2d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f5d2d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f5d2d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f5d2d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f5d2d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="f5d2d-110">Called by:</span></span>  <br/> |<span data-ttu-id="f5d2d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="f5d2d-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="f5d2d-112">参数</span><span class="sxs-lookup"><span data-stu-id="f5d2d-112">Parameters</span></span>

 <span data-ttu-id="f5d2d-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-113">_lpInterface_</span></span>
  
> <span data-ttu-id="f5d2d-114">[in]指向表数据对象的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-114">[in] Pointer to an interface identifier (IID) for the table data object.</span></span> <span data-ttu-id="f5d2d-115">有效的接口标识符是 IID_IMAPITableData。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-115">The valid interface identifier is IID_IMAPITableData.</span></span> <span data-ttu-id="f5d2d-116">_LpInterface_参数中传递 NULL 还会导致_lppTableData_参数将强制转换为标准接口表数据对象中返回的表数据对象。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-116">Passing NULL in the  _lpInterface_ parameter also causes the table data object returned in the  _lppTableData_ parameter to be cast to the standard interface for a table data object.</span></span> 
    
 <span data-ttu-id="f5d2d-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="f5d2d-118">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="f5d2d-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="f5d2d-120">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="f5d2d-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="f5d2d-122">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="f5d2d-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="f5d2d-124">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="f5d2d-125">_ulTableType_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-125">_ulTableType_</span></span>
  
> <span data-ttu-id="f5d2d-126">[in]可供客户端应用程序或服务提供商作为其表视图上的[IMAPITable::GetStatus](imapitable-getstatus.md)返回数据的一部分表类型。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-126">[in] A table type that is available to a client application or service provider as part of the [IMAPITable::GetStatus](imapitable-getstatus.md) return data on its table views.</span></span> <span data-ttu-id="f5d2d-127">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="f5d2d-127">Possible values are:</span></span> 
    
<span data-ttu-id="f5d2d-128">TBLTYPE_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="f5d2d-128">TBLTYPE_DYNAMIC</span></span> 
  
> <span data-ttu-id="f5d2d-129">表的内容是动态，并且可以更改基础数据集更改。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-129">The table's contents are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="f5d2d-130">TBLTYPE_KEYSET</span><span class="sxs-lookup"><span data-stu-id="f5d2d-130">TBLTYPE_KEYSET</span></span> 
  
> <span data-ttu-id="f5d2d-131">表中的行固定的但这些行中的值是动态，并可以更改基础数据集更改。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-131">The rows in the table are fixed, but the values in these rows are dynamic and can change as the underlying data changes.</span></span> 
    
<span data-ttu-id="f5d2d-132">TBLTYPE_SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="f5d2d-132">TBLTYPE_SNAPSHOT</span></span> 
  
> <span data-ttu-id="f5d2d-133">表是静态的在基础数据更改时不更改内容。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-133">The table is static and the contents do not change when the underlying data changes.</span></span> 
    
 <span data-ttu-id="f5d2d-134">_ulPropTagIndexColumn_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-134">_ulPropTagIndexColumn_</span></span>
  
> <span data-ttu-id="f5d2d-135">[in]更改表数据时使用的列的索引号。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-135">[in] Index number of the column for use when changing table data.</span></span> 
    
 <span data-ttu-id="f5d2d-136">_lpSPropTagArrayColumns_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-136">_lpSPropTagArrayColumns_</span></span>
  
> <span data-ttu-id="f5d2d-137">[in]指向[SPropTagArray](sproptagarray.md)结构，其中包含数组属性标记，指示其对象包含数据的表中所需的属性。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-137">[in] Pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags indicating the properties required in the table for which the object holds data.</span></span> 
    
 <span data-ttu-id="f5d2d-138">_lppTableData_</span><span class="sxs-lookup"><span data-stu-id="f5d2d-138">_lppTableData_</span></span>
  
> <span data-ttu-id="f5d2d-139">[输出]指向对返回的表格数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-139">[out] Pointer to a pointer to the returned table data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f5d2d-140">返回值</span><span class="sxs-lookup"><span data-stu-id="f5d2d-140">Return value</span></span>

<span data-ttu-id="f5d2d-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5d2d-141">S_OK</span></span> 
  
> <span data-ttu-id="f5d2d-142">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-142">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f5d2d-143">说明</span><span class="sxs-lookup"><span data-stu-id="f5d2d-143">Remarks</span></span>

<span data-ttu-id="f5d2d-144">_LpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)，和[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-144">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="f5d2d-145">调用**CreateTable**客户端应用程序中指针传递给 MAPI 函数只名为;服务提供商将指针传递给它在其初始化呼叫中收到或与调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。</span><span class="sxs-lookup"><span data-stu-id="f5d2d-145">A client application calling **CreateTable** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions that it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f5d2d-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5d2d-146">See also</span></span>



[<span data-ttu-id="f5d2d-147">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5d2d-147">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

