---
title: IMAPISessionEnumAdrTypes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.EnumAdrTypes
api_type:
- COM
ms.assetid: 9a3702a4-8a6b-4c0c-a90f-02be3a2bfa05
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6bd13eb7180302a5ab770586cf36856ca5a22676
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775548"
---
# <a name="imapisessionenumadrtypes"></a><span data-ttu-id="238de-103">IMAPISession::EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="238de-103">IMAPISession::EnumAdrTypes</span></span>

  
  
<span data-ttu-id="238de-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="238de-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="238de-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="238de-105">Deprecated.</span></span> <span data-ttu-id="238de-106">返回会话中的所有传输提供程序可以处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="238de-106">Returns the address types that can be handled by all of the transport providers in the session.</span></span> 
  
```cpp
HRESULT EnumAdrTypes(
  ULONG ulFlags,
  ULONG FAR * lpcAdrTypes,
  LPSTR FAR * FAR * lpppszAdrTypes
);
```

## <a name="parameters"></a><span data-ttu-id="238de-107">参数</span><span class="sxs-lookup"><span data-stu-id="238de-107">Parameters</span></span>

 <span data-ttu-id="238de-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="238de-108">_ulFlags_</span></span>
  
> <span data-ttu-id="238de-109">[in]位掩码的标志，指示返回的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="238de-109">[in] A bitmask of flags that indicates the format for the returned address types.</span></span> <span data-ttu-id="238de-110">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="238de-110">The following flag can be set:</span></span>
    
<span data-ttu-id="238de-111">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="238de-111">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="238de-112">地址类型的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="238de-112">The address types are in Unicode format.</span></span> <span data-ttu-id="238de-113">如果未设置 MAPI_UNICODE 标志，地址类型的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="238de-113">If the MAPI_UNICODE flag is not set, the address types are in ANSI format.</span></span>
    
 <span data-ttu-id="238de-114">_lpcAdrTypes_</span><span class="sxs-lookup"><span data-stu-id="238de-114">_lpcAdrTypes_</span></span>
  
> <span data-ttu-id="238de-115">[输出]一个指向_lpppszAdrTypes_参数指向的地址类型的计数。</span><span class="sxs-lookup"><span data-stu-id="238de-115">[out] A pointer to a count of address types pointed to by the  _lpppszAdrTypes_ parameter.</span></span> 
    
 <span data-ttu-id="238de-116">_lpppszAdrTypes_</span><span class="sxs-lookup"><span data-stu-id="238de-116">_lpppszAdrTypes_</span></span>
  
> <span data-ttu-id="238de-117">[输出]指向数组的指向地址类型的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="238de-117">[out] A pointer to an array of pointers to address types.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="238de-118">返回值</span><span class="sxs-lookup"><span data-stu-id="238de-118">Return value</span></span>

<span data-ttu-id="238de-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="238de-119">S_OK</span></span> 
  
> <span data-ttu-id="238de-120">已成功检索地址类型。</span><span class="sxs-lookup"><span data-stu-id="238de-120">The address types were successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="238de-121">说明</span><span class="sxs-lookup"><span data-stu-id="238de-121">Remarks</span></span>

<span data-ttu-id="238de-122">**IMAPISession::EnumAdrTypes**方法返回会话中的所有活动传输提供程序可以处理的地址类型列表。</span><span class="sxs-lookup"><span data-stu-id="238de-122">The **IMAPISession::EnumAdrTypes** method returns a list of the address types that can be handled by all of the active transport providers in the session.</span></span> <span data-ttu-id="238de-123">当前未加载的传输提供程序的地址类型不包含在该列表中。</span><span class="sxs-lookup"><span data-stu-id="238de-123">The address types for transport providers that are not currently loaded are not included in the list.</span></span> <span data-ttu-id="238de-124">传输提供程序注册，以处理时 MAPI 调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法的一个或多个地址类型。</span><span class="sxs-lookup"><span data-stu-id="238de-124">Transport providers register to handle one or more address types when MAPI calls their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="238de-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="238de-125">Notes to callers</span></span>

<span data-ttu-id="238de-126">调用[MAPIFreeBuffer](mapifreebuffer.md)释放_lpppszAdrTypes_参数指向的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="238de-126">Call [MAPIFreeBuffer](mapifreebuffer.md) to release the string array pointed to by the  _lpppszAdrTypes_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="238de-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="238de-127">See also</span></span>



[<span data-ttu-id="238de-128">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="238de-128">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="238de-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="238de-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="238de-130">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="238de-130">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

