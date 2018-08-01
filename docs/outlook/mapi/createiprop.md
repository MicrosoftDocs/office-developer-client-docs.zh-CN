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
ms.openlocfilehash: 906dc4a24b994e079a977808c3f501aaaea9d84f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774728"
---
# <a name="createiprop"></a><span data-ttu-id="d5068-103">CreateIProp</span><span class="sxs-lookup"><span data-stu-id="d5068-103">CreateIProp</span></span>

  
  
<span data-ttu-id="d5068-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d5068-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d5068-105">创建属性的数据对象，即[IPropData](ipropdataimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d5068-105">Creates a property data object, that is, an [IPropData](ipropdataimapiprop.md) object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d5068-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d5068-106">Header file:</span></span>  <br/> |<span data-ttu-id="d5068-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="d5068-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d5068-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="d5068-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d5068-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d5068-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d5068-110">调用：</span><span class="sxs-lookup"><span data-stu-id="d5068-110">Called by:</span></span>  <br/> |<span data-ttu-id="d5068-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d5068-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="d5068-112">参数</span><span class="sxs-lookup"><span data-stu-id="d5068-112">Parameters</span></span>

 <span data-ttu-id="d5068-113">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="d5068-113">_lpInterface_</span></span>
  
> <span data-ttu-id="d5068-114">[in]指向属性数据对象的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="d5068-114">[in] Pointer to an interface identifier (IID) for the property data object.</span></span> <span data-ttu-id="d5068-115">有效的接口标识符是 IID_IMAPIPropData。</span><span class="sxs-lookup"><span data-stu-id="d5068-115">The valid interface identifier is IID_IMAPIPropData.</span></span> <span data-ttu-id="d5068-116">_LpInterface_参数中传递 NULL 还会导致_lppPropData_参数可强制转换到标准界面属性的数据对象中返回的属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="d5068-116">Passing NULL in the  _lpInterface_ parameter also causes the property data object returned in the  _lppPropData_ parameter to be cast to the standard interface for a property data object.</span></span> 
    
 <span data-ttu-id="d5068-117">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="d5068-117">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="d5068-118">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="d5068-118">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="d5068-119">_lpAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="d5068-119">_lpAllocateMore_</span></span>
  
> <span data-ttu-id="d5068-120">[in]指向[MAPIAllocateMore](mapiallocatemore.md)函数，以用于分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="d5068-120">[in] Pointer to the [MAPIAllocateMore](mapiallocatemore.md) function, to be used to allocate additional memory.</span></span> 
    
 <span data-ttu-id="d5068-121">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="d5068-121">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="d5068-122">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="d5068-122">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="d5068-123">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="d5068-123">_lpvReserved_</span></span>
  
> <span data-ttu-id="d5068-124">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="d5068-124">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="d5068-125">_lppPropData_</span><span class="sxs-lookup"><span data-stu-id="d5068-125">_lppPropData_</span></span>
  
> <span data-ttu-id="d5068-126">[输出]指向对返回的属性数据对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d5068-126">[out] Pointer to a pointer to the returned property data object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d5068-127">返回值</span><span class="sxs-lookup"><span data-stu-id="d5068-127">Return value</span></span>

<span data-ttu-id="d5068-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5068-128">S_OK</span></span> 
  
> <span data-ttu-id="d5068-129">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="d5068-129">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="d5068-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="d5068-130">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="d5068-131">此对象不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="d5068-131">The requested interface is not supported for this object.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d5068-132">说明</span><span class="sxs-lookup"><span data-stu-id="d5068-132">Remarks</span></span>

<span data-ttu-id="d5068-133">_LpAllocateBuffer_、 _lpAllocateMore_和_lpFreeBuffer_输入的参数分别指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)，和[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d5068-133">The  _lpAllocateBuffer_,  _lpAllocateMore_, and  _lpFreeBuffer_ input parameters point to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) functions, respectively.</span></span> <span data-ttu-id="d5068-134">调用**CreateIProp**客户端应用程序中指针传递给 MAPI 函数只名为;服务提供商将指针传递给它在其初始化呼叫中收到或与调用[IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md)方法检索这些函数。</span><span class="sxs-lookup"><span data-stu-id="d5068-134">A client application calling **CreateIProp** passes in pointers to the MAPI functions just named; a service provider passes the pointers to these functions it received in its initialization call or retrieved with a call to the [IMAPISupport::GetMemAllocRoutines](imapisupport-getmemallocroutines.md) method.</span></span> 
  

