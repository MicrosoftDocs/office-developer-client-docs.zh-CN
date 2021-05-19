---
title: IMAPIProviderShutdownQueryFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.QueryFastShutdown
api_type:
- COM
ms.assetid: 12069912-4b87-4945-9123-51106e0d2d54
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 50b49761cf5923b11a450cbce7b7991f5ddd4d82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418216"
---
# <a name="imapiprovidershutdownqueryfastshutdown"></a><span data-ttu-id="d7cc2-103">IMAPIProviderShutdown::QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="d7cc2-103">IMAPIProviderShutdown::QueryFastShutdown</span></span>

  
  
<span data-ttu-id="d7cc2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7cc2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7cc2-105">向 MAPI 提供程序查询快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-105">Queries the MAPI provider for fast shutdown support.</span></span> 
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="d7cc2-106">返回值</span><span class="sxs-lookup"><span data-stu-id="d7cc2-106">Return value</span></span>

<span data-ttu-id="d7cc2-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7cc2-107">S_OK</span></span>
  
> <span data-ttu-id="d7cc2-108">MAPI 提供程序支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-108">The MAPI provider supports the MAPI client to do fast shutdown.</span></span>
    
<span data-ttu-id="d7cc2-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d7cc2-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="d7cc2-110">MAPI 提供程序不支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-110">The MAPI provider does not support the MAPI client to do fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7cc2-111">备注</span><span class="sxs-lookup"><span data-stu-id="d7cc2-111">Remarks</span></span>

<span data-ttu-id="d7cc2-112">无需支持客户端快速关闭的 MAPI 提供程序仍应实现 [IMAPIProviderShutdown](imapiprovidershutdowniunknown.md) 接口，并且让 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-112">MAPI providers that do not need to support client fast shutdown should still implement the [IMAPIProviderShutdown](imapiprovidershutdowniunknown.md) interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="d7cc2-113">对于Outlook MAPI 客户端，这将导致Outlook等待所有外部引用在退出之前释放。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-113">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="d7cc2-114">根据用户的快速关闭Windows设置，不实现 **IMAPIProviderShutdown** 接口不一定阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="d7cc2-114">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7cc2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7cc2-115">See also</span></span>



[<span data-ttu-id="d7cc2-116">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7cc2-116">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="d7cc2-117">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="d7cc2-117">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

