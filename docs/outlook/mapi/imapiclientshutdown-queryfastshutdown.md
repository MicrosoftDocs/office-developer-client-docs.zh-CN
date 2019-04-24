---
title: IMAPIClientShutdownQueryFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.QueryFastShutdown
api_type:
- COM
ms.assetid: b743b5b6-4a7c-46b8-99eb-afd13ee947db
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6a76488f56f9d1eb1b344c01de2615627dd5d3ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350867"
---
# <a name="imapiclientshutdownqueryfastshutdown"></a><span data-ttu-id="24a77-103">IMAPIClientShutdown::QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="24a77-103">IMAPIClientShutdown::QueryFastShutdown</span></span>

  
  
<span data-ttu-id="24a77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24a77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24a77-105">查询 mapi 子系统以获取加载的 mapi 提供程序提供的快速关闭支持。</span><span class="sxs-lookup"><span data-stu-id="24a77-105">Queries the MAPI subsystem for fast shutdown support that is provided by loaded MAPI providers.</span></span>
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="24a77-106">返回值</span><span class="sxs-lookup"><span data-stu-id="24a77-106">Return value</span></span>

<span data-ttu-id="24a77-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="24a77-107">S_OK</span></span>
  
> <span data-ttu-id="24a77-108">mapi 子系统支持 mapi 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="24a77-108">The MAPI subsystem supports the MAPI client to do fast shutdown.</span></span>
    
<span data-ttu-id="24a77-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="24a77-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="24a77-110">mapi 提供程序不支持 mapi 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="24a77-110">The MAPI provider does not support the MAPI client to do fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="24a77-111">注解</span><span class="sxs-lookup"><span data-stu-id="24a77-111">Remarks</span></span>

<span data-ttu-id="24a77-112">mapi 子系统是否支持对 mapi 客户端进行快速关闭取决于用户的 Windows 注册表设置或 mapi 客户端的默认行为以便快速关闭。</span><span class="sxs-lookup"><span data-stu-id="24a77-112">Whether the MAPI subsystem supports the MAPI client to do fast shutdown depends on the user's Windows registry setting or the default behavior of the MAPI client for fast shutdown.</span></span> <span data-ttu-id="24a77-113">它还取决于加载的 MAPI 提供程序支持快速关闭的功能。</span><span class="sxs-lookup"><span data-stu-id="24a77-113">It also depends on the ability of the loaded MAPI providers to support fast shutdown.</span></span> <span data-ttu-id="24a77-114">有关详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="24a77-114">For more information, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24a77-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24a77-115">See also</span></span>



[<span data-ttu-id="24a77-116">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="24a77-116">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="24a77-117">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="24a77-117">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

