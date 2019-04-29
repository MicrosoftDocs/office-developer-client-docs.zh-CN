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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3b2e41c4b1bfc4879717df0c73bbcd45a724ca60
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439287"
---
# <a name="imapisessionenumadrtypes"></a><span data-ttu-id="13b51-103">IMAPISession::EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="13b51-103">IMAPISession::EnumAdrTypes</span></span>

  
  
<span data-ttu-id="13b51-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13b51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13b51-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="13b51-105">Deprecated.</span></span> <span data-ttu-id="13b51-106">返回会话中的所有传输提供程序可以处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="13b51-106">Returns the address types that can be handled by all of the transport providers in the session.</span></span> 
  
```cpp
HRESULT EnumAdrTypes(
  ULONG ulFlags,
  ULONG FAR * lpcAdrTypes,
  LPSTR FAR * FAR * lpppszAdrTypes
);
```

## <a name="parameters"></a><span data-ttu-id="13b51-107">参数</span><span class="sxs-lookup"><span data-stu-id="13b51-107">Parameters</span></span>

 <span data-ttu-id="13b51-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="13b51-108">_ulFlags_</span></span>
  
> <span data-ttu-id="13b51-109">实时标志的位掩码, 指示返回的地址类型的格式。</span><span class="sxs-lookup"><span data-stu-id="13b51-109">[in] A bitmask of flags that indicates the format for the returned address types.</span></span> <span data-ttu-id="13b51-110">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="13b51-110">The following flag can be set:</span></span>
    
<span data-ttu-id="13b51-111">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="13b51-111">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="13b51-112">地址类型为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="13b51-112">The address types are in Unicode format.</span></span> <span data-ttu-id="13b51-113">如果未设置 MAPI_UNICODE 标志, 则地址类型将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="13b51-113">If the MAPI_UNICODE flag is not set, the address types are in ANSI format.</span></span>
    
 <span data-ttu-id="13b51-114">_lpcAdrTypes_</span><span class="sxs-lookup"><span data-stu-id="13b51-114">_lpcAdrTypes_</span></span>
  
> <span data-ttu-id="13b51-115">排除一个指针, 指向_lpppszAdrTypes_参数指向的地址类型的计数。</span><span class="sxs-lookup"><span data-stu-id="13b51-115">[out] A pointer to a count of address types pointed to by the  _lpppszAdrTypes_ parameter.</span></span> 
    
 <span data-ttu-id="13b51-116">_lpppszAdrTypes_</span><span class="sxs-lookup"><span data-stu-id="13b51-116">_lpppszAdrTypes_</span></span>
  
> <span data-ttu-id="13b51-117">排除指向指向地址类型的指针数组的指针。</span><span class="sxs-lookup"><span data-stu-id="13b51-117">[out] A pointer to an array of pointers to address types.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="13b51-118">返回值</span><span class="sxs-lookup"><span data-stu-id="13b51-118">Return value</span></span>

<span data-ttu-id="13b51-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="13b51-119">S_OK</span></span> 
  
> <span data-ttu-id="13b51-120">已成功检索地址类型。</span><span class="sxs-lookup"><span data-stu-id="13b51-120">The address types were successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="13b51-121">说明</span><span class="sxs-lookup"><span data-stu-id="13b51-121">Remarks</span></span>

<span data-ttu-id="13b51-122">**IMAPISession:: EnumAdrTypes**方法返回会话中所有活动的传输提供程序可以处理的地址类型的列表。</span><span class="sxs-lookup"><span data-stu-id="13b51-122">The **IMAPISession::EnumAdrTypes** method returns a list of the address types that can be handled by all of the active transport providers in the session.</span></span> <span data-ttu-id="13b51-123">当前未加载的传输提供程序的地址类型不包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="13b51-123">The address types for transport providers that are not currently loaded are not included in the list.</span></span> <span data-ttu-id="13b51-124">当 MAPI 调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法时, 传输提供程序将注册以处理一个或多个地址类型。</span><span class="sxs-lookup"><span data-stu-id="13b51-124">Transport providers register to handle one or more address types when MAPI calls their [IXPLogon::AddressTypes](ixplogon-addresstypes.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="13b51-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="13b51-125">Notes to callers</span></span>

<span data-ttu-id="13b51-126">调用[MAPIFreeBuffer](mapifreebuffer.md)以释放_lpppszAdrTypes_参数指向的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="13b51-126">Call [MAPIFreeBuffer](mapifreebuffer.md) to release the string array pointed to by the  _lpppszAdrTypes_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="13b51-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13b51-127">See also</span></span>



[<span data-ttu-id="13b51-128">IXPLogon::AddressTypes</span><span class="sxs-lookup"><span data-stu-id="13b51-128">IXPLogon::AddressTypes</span></span>](ixplogon-addresstypes.md)
  
[<span data-ttu-id="13b51-129">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="13b51-129">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="13b51-130">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="13b51-130">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

