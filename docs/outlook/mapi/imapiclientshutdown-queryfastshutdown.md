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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 784a2f497811ba7c4ba0abf260ff32fde75de76a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584931"
---
# <a name="imapiclientshutdownqueryfastshutdown"></a><span data-ttu-id="b6f01-103">IMAPIClientShutdown::QueryFastShutdown</span><span class="sxs-lookup"><span data-stu-id="b6f01-103">IMAPIClientShutdown::QueryFastShutdown</span></span>

  
  
<span data-ttu-id="b6f01-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6f01-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6f01-105">查询的 MAPI 子系统的快速关闭支持提供的加载 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b6f01-105">Queries the MAPI subsystem for fast shutdown support that is provided by loaded MAPI providers.</span></span>
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="b6f01-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b6f01-106">Return value</span></span>

<span data-ttu-id="b6f01-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6f01-107">S_OK</span></span>
  
> <span data-ttu-id="b6f01-108">MAPI 子系统支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="b6f01-108">The MAPI subsystem supports the MAPI client to do fast shutdown.</span></span>
    
<span data-ttu-id="b6f01-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b6f01-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="b6f01-110">MAPI 提供程序不支持 MAPI 客户端执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="b6f01-110">The MAPI provider does not support the MAPI client to do fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b6f01-111">注解</span><span class="sxs-lookup"><span data-stu-id="b6f01-111">Remarks</span></span>

<span data-ttu-id="b6f01-112">MAPI 子系统是否支持 MAPI 客户端执行快速关闭取决于用户的 Windows 注册表设置或 MAPI 客户端的快速关闭的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b6f01-112">Whether the MAPI subsystem supports the MAPI client to do fast shutdown depends on the user's Windows registry setting or the default behavior of the MAPI client for fast shutdown.</span></span> <span data-ttu-id="b6f01-113">它还依靠加载 MAPI 提供程序支持快速关闭的能力。</span><span class="sxs-lookup"><span data-stu-id="b6f01-113">It also depends on the ability of the loaded MAPI providers to support fast shutdown.</span></span> <span data-ttu-id="b6f01-114">有关详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。</span><span class="sxs-lookup"><span data-stu-id="b6f01-114">For more information, see [Fast Shutdown User Options](fast-shutdown-user-options.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6f01-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6f01-115">See also</span></span>



[<span data-ttu-id="b6f01-116">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6f01-116">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="b6f01-117">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="b6f01-117">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

