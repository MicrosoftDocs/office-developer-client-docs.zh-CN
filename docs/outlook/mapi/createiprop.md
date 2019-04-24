---
title: CreateIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CreateIProp
api_type:
- COM
ms.assetid: 9bf68814-2564-433d-b762-3d2c83ca3c60
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e318d7a709a09e67ebf423db0263985523d2fc28
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333031"
---
# <a name="createiprop"></a><span data-ttu-id="65b77-103">CreateIProp</span><span class="sxs-lookup"><span data-stu-id="65b77-103">CreateIProp</span></span>

  
  
<span data-ttu-id="65b77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65b77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65b77-105">创建一个属性数据对象, 即一个[IPropData](ipropdataimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="65b77-105">Creates a property data object, that is, an [IPropData](ipropdataimapiprop.md) object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="65b77-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="65b77-106">Header file:</span></span>  <br/> |<span data-ttu-id="65b77-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="65b77-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="65b77-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="65b77-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="65b77-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="65b77-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="65b77-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="65b77-110">Called by:</span></span>  <br/> |<span data-ttu-id="65b77-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="65b77-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE CreateIProp(
  LPCIID lpInterface,
  ALLOCATEBUFFER FAR * lpAllocateBuffer,
  ALLOCATEMORE FAR * lpAllocateMore,
  FREEBUFFER FAR * lpFreeBuffer,
  LPVOID lpvReserved,
  LPPROPDATA FAR * lppPropData
);
```

## <a name="parameters"></a><span data-ttu-id="65b77-112">参数</span><span class="sxs-lookup"><span data-stu-id="65b77-112">Parameters</span></span>

 <span data-ttu-id="65b77-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="65b77-113">_lpInterface_</span></span>
  
> <span data-ttu-id="65b77-114">实时指向属性数据对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="65b77-114">[in] Pointer to an interface identifier (IID) for the property data object.</span></span> <span data-ttu-id="65b77-115">有效的接口标识符为 IID_IMAPIPropData。</span><span class="sxs-lookup"><span data-stu-id="65b77-115">The valid interface identifier is IID_IMAPIPropData.</span></span> <span data-ttu-id="65b77-116">在_lpInterface_参数中传递 NULL 还会导致在_lppPropData_参数中返回的属性数据对象将转换为属性数据对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="65b77-116">Passing NULL in the  _lpInterface_ parameter also causes the property data object returned in the  _lppPropData_ parameter to be cast to the standard interface for a property data object.</span></span> 
    
 <span data-ttu-id="65b77-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="65b77-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="65b77-118">实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="65b77-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="65b77-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="65b77-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="65b77-120">实时指向[MAPIAllocateMore](mapiallocatemore.md)函数的指针, 该函数用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="65b77-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="65b77-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="65b77-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="65b77-122">实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。</span><span class="sxs-lookup"><span data-stu-id="65b77-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="65b77-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="65b77-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="65b77-124">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="65b77-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="65b77-125">_lppPropData_</span><span class="sxs-lookup"><span data-stu-id="65b77-125">_lppPropData_</span></span>
  
> <span data-ttu-id="65b77-126">排除指向返回的属性数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="65b77-126">[out] Pointer to a pointer to the returned property data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="65b77-127">返回值</span><span class="sxs-lookup"><span data-stu-id="65b77-127">Return value</span></span>

<span data-ttu-id="65b77-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="65b77-128">S_OK</span></span> 
  
> <span data-ttu-id="65b77-129">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="65b77-129">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="65b77-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="65b77-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="65b77-131">此对象不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="65b77-131">The requested interface is not supported for this object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="65b77-132">注解</span><span class="sxs-lookup"><span data-stu-id="65b77-132">Remarks</span></span>

<span data-ttu-id="65b77-133">" _lpAllocateBuffer_"、" _lpAllocateMore_" 和 " _lpFreeBuffer_ " 输入参数分别指向 " [MAPIAllocateBuffer](mapiallocatebuffer.md)"、" [MAPIAllocateMore](mapiallocatemore.md)" 和 " [MAPIFreeBuffer](mapifreebuffer.md) " 函数。</span><span class="sxs-lookup"><span data-stu-id="65b77-133">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="65b77-134">调用**CreateIProp**的客户端应用程序传递到刚刚命名的 MAPI 函数的指针。服务提供程序将指针传递给其在初始化调用中收到的这些函数, 或通过调用[IMAPISupport:: GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索到这些函数。</span><span class="sxs-lookup"><span data-stu-id="65b77-134">A client application calling **CreateIProp** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  

