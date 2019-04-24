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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338484"
---
# <a name="imapiprovidershutdownqueryfastshutdown"></a><span data-ttu-id="9ce34-103">IMAPIProviderShutdown::QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="9ce34-103">IMAPIProviderShutdown::QueryFastShutdown</span></span>

  
  
<span data-ttu-id="9ce34-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ce34-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ce34-105">查询 MAPI 提供程序以获取快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="9ce34-105">Queries the MAPI provider for fast shutdown support.</span></span> 
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="9ce34-106">返回值</span><span class="sxs-lookup"><span data-stu-id="9ce34-106">Return value</span></span>

<span data-ttu-id="9ce34-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ce34-107">S_OK</span></span>
  
> <span data-ttu-id="9ce34-108">mapi 提供程序支持 mapi 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="9ce34-108">The MAPI provider supports the MAPI client to do fast shutdown.</span></span>
    
<span data-ttu-id="9ce34-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="9ce34-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="9ce34-110">mapi 提供程序不支持 mapi 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="9ce34-110">The MAPI provider does not support the MAPI client to do fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9ce34-111">注解</span><span class="sxs-lookup"><span data-stu-id="9ce34-111">Remarks</span></span>

<span data-ttu-id="9ce34-112">如果 MAPI 提供程序不需要支持客户端快速关闭, 则仍应实现[IMAPIProviderShutdown](imapiprovidershutdowniunknown.md)接口, 并让**IMAPIProviderShutdown:: QueryFastShutdown**方法返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="9ce34-112">MAPI providers that do not need to support client fast shutdown should still implement the [IMAPIProviderShutdown](imapiprovidershutdowniunknown.md) interface, and have the **IMAPIProviderShutdown::QueryFastShutdown** method return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="9ce34-113">对于 outlook 作为 MAPI 客户端, 这会导致 Outlook 等待所有外部引用在退出之前发布。</span><span class="sxs-lookup"><span data-stu-id="9ce34-113">For Outlook as a MAPI client, this causes Outlook to wait for all external references to be released before it exits.</span></span> 
  
<span data-ttu-id="9ce34-114">根据用户的 Windows 注册表设置快速关闭, 不实现**IMAPIProviderShutdown**接口不一定会阻止客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="9ce34-114">Depending on the user's Windows registry setting for fast shutdown, not implementing the **IMAPIProviderShutdown** interface does not necessarily prevent a client fast shutdown.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9ce34-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ce34-115">See also</span></span>



[<span data-ttu-id="9ce34-116">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9ce34-116">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="9ce34-117">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="9ce34-117">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

