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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4301fb504439cf0ebd70b5ece589c812cb74844e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585295"
---
# <a name="imapiprovidershutdownqueryfastshutdown"></a><span data-ttu-id="de497-103">IMAPIProviderShutdown::QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="de497-103">IMAPIProviderShutdown::QueryFastShutdown</span></span>

  
  
<span data-ttu-id="de497-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="de497-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="de497-105">查询快速关闭 MAPI 提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="de497-105">Queries the MAPI provider for fast shutdown support.</span></span> 
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="de497-106">返回值</span><span class="sxs-lookup"><span data-stu-id="de497-106">Return value</span></span>

<span data-ttu-id="de497-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="de497-107">S_OK</span></span>
  
> <span data-ttu-id="de497-108">MAPI 提供程序支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="de497-108">The MAPI provider supports the MAPI client to do fast shutdown.</span></span>
    
<span data-ttu-id="de497-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="de497-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="de497-110">MAPI 提供程序不支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="de497-110">The MAPI provider does not support the MAPI client to do fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="de497-111">注解</span><span class="sxs-lookup"><span data-stu-id="de497-111">Remarks</span></span>

<span data-ttu-id="de497-112">MAPI 提供程序不需要支持客户端快速关闭仍应实现[IMAPIProviderShutdown](imapiprovidershutdowniunknown.md)接口，并让 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="de497-112">MAPI providers that do not need to support client fast shutdown should still implement the [IMAPIProviderShutdown](imapiprovidershutdowniunknown.md) interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="de497-113">对于作为 MAPI 客户端的 Outlook，这会导致 Outlook 等待它退出之前，必须释放的所有外部引用。</span><span class="sxs-lookup"><span data-stu-id="de497-113">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="de497-114">根据用户的 Windows 注册表设置的快速关闭不实现**IMAPIProviderShutdown**接口不一定是阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="de497-114">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="de497-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de497-115">See also</span></span>



[<span data-ttu-id="de497-116">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="de497-116">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="de497-117">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="de497-117">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

