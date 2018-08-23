---
title: IMAPIOfflineMgrAdvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr.Advise
api_type:
- COM
ms.assetid: 784b6218-548d-817a-caaa-cf9be6bc3d2f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e0c8c4c6251581506c7bdd78c009bb12e8291c81
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586933"
---
# <a name="imapiofflinemgradvise"></a><span data-ttu-id="969f3-103">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="969f3-103">IMAPIOfflineMgr::Advise</span></span>

  
  
<span data-ttu-id="969f3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="969f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="969f3-105">注册接收回调脱机对象上的客户端。</span><span class="sxs-lookup"><span data-stu-id="969f3-105">Registers a client to receive callbacks on an offline object.</span></span>
  
```cpp
HRESULT COfflineObj::Advise( 
      ULONG ulFlags, 
      MAPIOFFLINE_ADVISEINFO* pAdviseInfo, 
      ULONG* pulAdviseToken 
);
```

## <a name="parameters"></a><span data-ttu-id="969f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="969f3-106">Parameters</span></span>

 <span data-ttu-id="969f3-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="969f3-107">_ulFlags_</span></span>
  
>  <span data-ttu-id="969f3-108">[in]修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="969f3-108">[in] Flags that modify behavior.</span></span> <span data-ttu-id="969f3-109">支持仅值 MAPIOFFLINE_ADVISE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="969f3-109">Only the value MAPIOFFLINE_ADVISE_DEFAULT is supported.</span></span> 
    
 <span data-ttu-id="969f3-110">_pAdviseInfo_</span><span class="sxs-lookup"><span data-stu-id="969f3-110">_pAdviseInfo_</span></span>
  
> <span data-ttu-id="969f3-111">[in]信息的类型回调，何时接收回调、 回调接口将呼叫者和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="969f3-111">[in] Information about the type of callback, when to receive a callback, a callback interface for the caller, and other details.</span></span> <span data-ttu-id="969f3-112">它还包含在向客户端呼叫者发送后续的通知回调中使用 Outlook 客户端令牌。</span><span class="sxs-lookup"><span data-stu-id="969f3-112">It also contains a client token that Outlook uses in sending subsequent notification callbacks to the client caller.</span></span>
    
 <span data-ttu-id="969f3-113">_pulAdviseToken_</span><span class="sxs-lookup"><span data-stu-id="969f3-113">_pulAdviseToken_</span></span>
  
> <span data-ttu-id="969f3-114">[输出]随后取消回调对象返回到客户端呼叫者 advise 令牌。</span><span class="sxs-lookup"><span data-stu-id="969f3-114">[out] An advise token returned to the client caller for subsequently canceling callback for the object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="969f3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="969f3-115">Return value</span></span>

<span data-ttu-id="969f3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="969f3-116">S_OK</span></span>
  
> <span data-ttu-id="969f3-117">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="969f3-117">The call was successful.</span></span>
    
<span data-ttu-id="969f3-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="969f3-118">E_INVALIDARG</span></span>
  
> <span data-ttu-id="969f3-119">已指定了无效的参数。</span><span class="sxs-lookup"><span data-stu-id="969f3-119">An invalid parameter has been specified.</span></span>
    
<span data-ttu-id="969f3-120">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="969f3-120">E_NOINTERFACE</span></span>
  
> <span data-ttu-id="969f3-121">*PAdviseInfo*中指定的回调接口无效。</span><span class="sxs-lookup"><span data-stu-id="969f3-121">The callback interface specified in  *pAdviseInfo*  is not valid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="969f3-122">注解</span><span class="sxs-lookup"><span data-stu-id="969f3-122">Remarks</span></span>

<span data-ttu-id="969f3-123">在打开时使用**[HrOpenOfflineObj](hropenofflineobj.md)** 脱机对象，客户端获取脱机支持**IMAPIOfflineMgr**的对象。</span><span class="sxs-lookup"><span data-stu-id="969f3-123">Upon opening an offline object using **[HrOpenOfflineObj](hropenofflineobj.md)**, a client obtains an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="969f3-124">客户端可以检查回调对象使用**[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** 支持的类型。</span><span class="sxs-lookup"><span data-stu-id="969f3-124">The client can check for the kinds of callbacks supported by the object by using **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)**.</span></span> <span data-ttu-id="969f3-125">类型以及其他有关回调其想，，然后调用**IMAPIOfflineMgr::Advise**进行注册，以接收此类回调有关对象的详细信息，可以确定客户端。</span><span class="sxs-lookup"><span data-stu-id="969f3-125">The client can determine the type and other details about the callback it wants, and then call **IMAPIOfflineMgr::Advise** to register to receive such callbacks about the object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="969f3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="969f3-126">See also</span></span>



[<span data-ttu-id="969f3-127">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="969f3-127">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="969f3-128">IMAPIOfflineMgr::Unadvise</span><span class="sxs-lookup"><span data-stu-id="969f3-128">IMAPIOfflineMgr::Unadvise</span></span>](imapiofflinemgr-unadvise.md)


[<span data-ttu-id="969f3-129">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="969f3-129">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="969f3-130">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="969f3-130">HrOpenOfflineObj</span></span>](hropenofflineobj.md)

