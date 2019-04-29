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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3ca7fdc39da8d3ee8ecf6f0f253284df10a392e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426917"
---
# <a name="imapiofflinemgradvise"></a><span data-ttu-id="1ad0d-103">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="1ad0d-103">IMAPIOfflineMgr::Advise</span></span>

  
  
<span data-ttu-id="1ad0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ad0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ad0d-105">注册客户端以接收对脱机对象的回调。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-105">Registers a client to receive callbacks on an offline object.</span></span>
  
```cpp
HRESULT COfflineObj::Advise( 
      ULONG ulFlags, 
      MAPIOFFLINE_ADVISEINFO* pAdviseInfo, 
      ULONG* pulAdviseToken 
);
```

## <a name="parameters"></a><span data-ttu-id="1ad0d-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ad0d-106">Parameters</span></span>

 <span data-ttu-id="1ad0d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1ad0d-107">_ulFlags_</span></span>
  
>  <span data-ttu-id="1ad0d-108">实时修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-108">[in] Flags that modify behavior.</span></span> <span data-ttu-id="1ad0d-109">仅支持值 MAPIOFFLINE_ADVISE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-109">Only the value MAPIOFFLINE_ADVISE_DEFAULT is supported.</span></span> 
    
 <span data-ttu-id="1ad0d-110">_pAdviseInfo_</span><span class="sxs-lookup"><span data-stu-id="1ad0d-110">_pAdviseInfo_</span></span>
  
> <span data-ttu-id="1ad0d-111">实时有关回调类型、何时接收回调、呼叫者的回调接口以及其他详细信息的信息。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-111">[in] Information about the type of callback, when to receive a callback, a callback interface for the caller, and other details.</span></span> <span data-ttu-id="1ad0d-112">它还包含 Outlook 在向客户端调用方发送后续通知回调时使用的客户端令牌。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-112">It also contains a client token that Outlook uses in sending subsequent notification callbacks to the client caller.</span></span>
    
 <span data-ttu-id="1ad0d-113">_pulAdviseToken_</span><span class="sxs-lookup"><span data-stu-id="1ad0d-113">_pulAdviseToken_</span></span>
  
> <span data-ttu-id="1ad0d-114">排除向客户端调用方返回的建议令牌, 随后取消对该对象的回调。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-114">[out] An advise token returned to the client caller for subsequently canceling callback for the object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1ad0d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="1ad0d-115">Return value</span></span>

<span data-ttu-id="1ad0d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ad0d-116">S_OK</span></span>
  
> <span data-ttu-id="1ad0d-117">调用成功。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-117">The call was successful.</span></span>
    
<span data-ttu-id="1ad0d-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1ad0d-118">E_INVALIDARG</span></span>
  
> <span data-ttu-id="1ad0d-119">指定的参数无效。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-119">An invalid parameter has been specified.</span></span>
    
<span data-ttu-id="1ad0d-120">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="1ad0d-120">E_NOINTERFACE</span></span>
  
> <span data-ttu-id="1ad0d-121">*pAdviseInfo*中指定的回调接口无效。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-121">The callback interface specified in  *pAdviseInfo*  is not valid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1ad0d-122">说明</span><span class="sxs-lookup"><span data-stu-id="1ad0d-122">Remarks</span></span>

<span data-ttu-id="1ad0d-123">使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开脱机对象时, 客户端将获得支持**IMAPIOfflineMgr**的脱机对象。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-123">Upon opening an offline object using **[HrOpenOfflineObj](hropenofflineobj.md)**, a client obtains an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="1ad0d-124">客户端可以使用**[IMAPIOffline:: GetCapabilities](imapioffline-getcapabilities.md)** 检查对象支持的回调的种类。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-124">The client can check for the kinds of callbacks supported by the object by using **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)**.</span></span> <span data-ttu-id="1ad0d-125">客户端可以确定它所需的回调的类型和其他详细信息, 然后调用**IMAPIOfflineMgr:: 建议**注册以接收有关对象的此类回调。</span><span class="sxs-lookup"><span data-stu-id="1ad0d-125">The client can determine the type and other details about the callback it wants, and then call **IMAPIOfflineMgr::Advise** to register to receive such callbacks about the object.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1ad0d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad0d-126">See also</span></span>



[<span data-ttu-id="1ad0d-127">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="1ad0d-127">IMAPIOffline::GetCapabilities</span></span>](imapioffline-getcapabilities.md)
  
[<span data-ttu-id="1ad0d-128">IMAPIOfflineMgr::Unadvise</span><span class="sxs-lookup"><span data-stu-id="1ad0d-128">IMAPIOfflineMgr::Unadvise</span></span>](imapiofflinemgr-unadvise.md)


[<span data-ttu-id="1ad0d-129">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="1ad0d-129">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="1ad0d-130">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="1ad0d-130">HrOpenOfflineObj</span></span>](hropenofflineobj.md)

