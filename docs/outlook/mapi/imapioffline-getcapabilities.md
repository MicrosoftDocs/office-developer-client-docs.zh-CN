---
title: IMAPIOfflineGetCapabilities
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.GetCapabilities
api_type:
- COM
ms.assetid: aa8dc48b-9e1c-8da0-9579-10b7174e99de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 48d59d17d81da2ae78348a57ad8b1cb75486b1a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433372"
---
# <a name="imapiofflinegetcapabilities"></a><span data-ttu-id="5871f-103">IMAPIOffline::GetCapabilities</span><span class="sxs-lookup"><span data-stu-id="5871f-103">IMAPIOffline::GetCapabilities</span></span>

  
  
<span data-ttu-id="5871f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5871f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5871f-105">获取脱机对象支持的回调的条件。</span><span class="sxs-lookup"><span data-stu-id="5871f-105">Gets the conditions for which callbacks are supported by an offline object.</span></span>
  
```cpp
HRESULT GetCapabilities( 
    ULONG *pulCapabilities 
);
```

## <a name="parameters"></a><span data-ttu-id="5871f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5871f-106">Parameters</span></span>

 <span data-ttu-id="5871f-107">_pulCapablities_</span><span class="sxs-lookup"><span data-stu-id="5871f-107">_pulCapablities_</span></span>
  
> <span data-ttu-id="5871f-108">排除以下功能标志的位掩码:</span><span class="sxs-lookup"><span data-stu-id="5871f-108">[out] A bitmask of the following capability flags:</span></span>
    
<span data-ttu-id="5871f-109">MAPIOFFLINE_CAPABILITY_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="5871f-109">MAPIOFFLINE_CAPABILITY_OFFLINE</span></span>
  
> <span data-ttu-id="5871f-110">脱机对象能够提供脱机通知。</span><span class="sxs-lookup"><span data-stu-id="5871f-110">The offline object is capable of providing offline notifications.</span></span>
    
<span data-ttu-id="5871f-111">MAPIOFFLINE_CAPABILITY_ONLINE</span><span class="sxs-lookup"><span data-stu-id="5871f-111">MAPIOFFLINE_CAPABILITY_ONLINE</span></span>
  
> <span data-ttu-id="5871f-112">脱机对象能够提供联机通知。</span><span class="sxs-lookup"><span data-stu-id="5871f-112">The offline object is capable of providing online notifications.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5871f-113">说明</span><span class="sxs-lookup"><span data-stu-id="5871f-113">Remarks</span></span>

<span data-ttu-id="5871f-114">在使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开脱机对象时, 客户端可以查询[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)以获取指向**IMAPIOffline**接口的指针, 并调用**IMAPIOffline:: GetCapabilities**以查找支持的回调对象。</span><span class="sxs-lookup"><span data-stu-id="5871f-114">Upon opening an offline object using **[HrOpenOfflineObj](hropenofflineobj.md)**, a client can query on [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md) to obtain a pointer to an **IMAPIOffline** interface, and call **IMAPIOffline::GetCapabilities** to find out the callbacks supported by the object.</span></span> <span data-ttu-id="5871f-115">然后, 客户端可以选择使用**IMAPIOfflineMgr**设置回调。</span><span class="sxs-lookup"><span data-stu-id="5871f-115">The client can then choose to set up callbacks by using **IMAPIOfflineMgr**.</span></span>
  
<span data-ttu-id="5871f-116">请注意, 根据脱机对象的邮件服务器, 支持联机的回调的对象不一定支持要脱机的回调。</span><span class="sxs-lookup"><span data-stu-id="5871f-116">Note that, depending on the mail server for an offline object, an object that supports callbacks for going online does not necessarily support callbacks for going offline.</span></span>
  
<span data-ttu-id="5871f-117">另请注意, 尽管脱机对象可能支持非联机/脱机更改的回调, 但脱机状态 API 仅支持联机/脱机更改, 并且客户端必须仅检查此类功能。</span><span class="sxs-lookup"><span data-stu-id="5871f-117">Also note that, while an offline object may support callbacks for changes other than online/offline, the Offline State API supports only online/offline changes, and clients must check for only such capabilities.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5871f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5871f-118">See also</span></span>



[<span data-ttu-id="5871f-119">IMAPIOffline::GetCurrentState</span><span class="sxs-lookup"><span data-stu-id="5871f-119">IMAPIOffline::GetCurrentState</span></span>](imapioffline-getcurrentstate.md)
  
[<span data-ttu-id="5871f-120">IMAPIOffline::SetCurrentState</span><span class="sxs-lookup"><span data-stu-id="5871f-120">IMAPIOffline::SetCurrentState</span></span>](imapioffline-setcurrentstate.md)
  
[<span data-ttu-id="5871f-121">IMAPIOfflineMgr : IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="5871f-121">IMAPIOfflineMgr : IMAPIOffline</span></span>](imapiofflinemgrimapioffline.md)


[<span data-ttu-id="5871f-122">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="5871f-122">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="5871f-123">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="5871f-123">HrOpenOfflineObj</span></span>](hropenofflineobj.md)

