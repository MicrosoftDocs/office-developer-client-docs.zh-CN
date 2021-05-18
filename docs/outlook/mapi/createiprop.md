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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406806"
---
# <a name="createiprop"></a><span data-ttu-id="617ed-103">CreateIProp</span><span class="sxs-lookup"><span data-stu-id="617ed-103">CreateIProp</span></span>

  
  
<span data-ttu-id="617ed-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="617ed-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="617ed-105">创建一个属性数据对象，即 [IPropData](ipropdataimapiprop.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="617ed-105">Creates a property data object, that is, an [IPropData](ipropdataimapiprop.md) object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="617ed-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="617ed-106">Header file:</span></span>  <br/> |<span data-ttu-id="617ed-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="617ed-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="617ed-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="617ed-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="617ed-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="617ed-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="617ed-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="617ed-110">Called by:</span></span>  <br/> |<span data-ttu-id="617ed-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="617ed-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="617ed-112">参数</span><span class="sxs-lookup"><span data-stu-id="617ed-112">Parameters</span></span>

 <span data-ttu-id="617ed-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="617ed-113">_lpInterface_</span></span>
  
> <span data-ttu-id="617ed-114">[in]指向属性数据 (IID) 接口标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="617ed-114">[in] Pointer to an interface identifier (IID) for the property data object.</span></span> <span data-ttu-id="617ed-115">有效的接口标识符IID_IMAPIPropData。</span><span class="sxs-lookup"><span data-stu-id="617ed-115">The valid interface identifier is IID_IMAPIPropData.</span></span> <span data-ttu-id="617ed-116">在  _lpInterface_ 参数中传递 NULL 还会导致  _在 lppPropData_ 参数中返回的属性数据对象强制转换到属性数据对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="617ed-116">Passing NULL in the  _lpInterface_ parameter also causes the property data object returned in the  _lppPropData_ parameter to be cast to the standard interface for a property data object.</span></span> 
    
 <span data-ttu-id="617ed-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="617ed-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="617ed-118">[in]指向 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数的指针，用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="617ed-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="617ed-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="617ed-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="617ed-120">[in]指向 [MAPIAllocateMore](mapiallocatemore.md) 函数的指针，用于分配额外的内存。</span><span class="sxs-lookup"><span data-stu-id="617ed-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="617ed-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="617ed-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="617ed-122">[in]指向 [MAPIFreeBuffer](mapifreebuffer.md) 函数的指针，用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="617ed-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="617ed-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="617ed-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="617ed-124">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="617ed-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="617ed-125">_lppPropData_</span><span class="sxs-lookup"><span data-stu-id="617ed-125">_lppPropData_</span></span>
  
> <span data-ttu-id="617ed-126">[out]指向返回的属性数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="617ed-126">[out] Pointer to a pointer to the returned property data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="617ed-127">返回值</span><span class="sxs-lookup"><span data-stu-id="617ed-127">Return value</span></span>

<span data-ttu-id="617ed-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="617ed-128">S_OK</span></span> 
  
> <span data-ttu-id="617ed-129">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="617ed-129">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="617ed-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="617ed-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="617ed-131">此对象不支持请求的接口。</span><span class="sxs-lookup"><span data-stu-id="617ed-131">The requested interface is not supported for this object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="617ed-132">备注</span><span class="sxs-lookup"><span data-stu-id="617ed-132">Remarks</span></span>

<span data-ttu-id="617ed-133">_lpAllocateBuffer、lpAllocateMore_ 和 _lpFreeBuffer_ 输入参数分别指向 [MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)函数。  [](mapiallocatemore.md)</span><span class="sxs-lookup"><span data-stu-id="617ed-133">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="617ed-134">调用 **CreateIProp** 的客户端应用程序将传递指向刚命名的 MAPI 函数的指针;服务提供商将指针传递给其在其初始化调用中收到的或通过调用 [IMAPISupport：：GetMemAllocRoutines](imapisupport-getmemallocroutines.md) 方法检索的函数。</span><span class="sxs-lookup"><span data-stu-id="617ed-134">A client application calling **CreateIProp** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  

