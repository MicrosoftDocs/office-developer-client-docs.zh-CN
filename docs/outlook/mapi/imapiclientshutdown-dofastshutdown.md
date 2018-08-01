---
title: IMAPIClientShutdownDoFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.DoFastShutdown
api_type:
- COM
ms.assetid: 310cba9a-a343-484d-a029-fcd51b731460
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 447832d88a9740875fcf39a32adcf4ebb99e05ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775313"
---
# <a name="imapiclientshutdowndofastshutdown"></a><span data-ttu-id="0f77c-103">IMAPIClientShutdown::DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="0f77c-103">IMAPIClientShutdown::DoFastShutdown</span></span>

  
  
<span data-ttu-id="0f77c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0f77c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0f77c-105">指示的 MAPI 客户端的目的立即退出该客户端进程。</span><span class="sxs-lookup"><span data-stu-id="0f77c-105">Indicates the intention of the MAPI client to exit the client process immediately.</span></span>
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="0f77c-106">返回值</span><span class="sxs-lookup"><span data-stu-id="0f77c-106">Return value</span></span>

<span data-ttu-id="0f77c-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f77c-107">S_OK</span></span>
  
> <span data-ttu-id="0f77c-108">立即退出 MAPI 客户端和 MAPI 提供程序可供客户端退出 MAPI 子系统表示到加载 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0f77c-108">The MAPI subsystem has indicated to loaded MAPI providers that the MAPI client is exiting immediately, and the MAPI providers are ready for the client exit.</span></span>
    
<span data-ttu-id="0f77c-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="0f77c-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="0f77c-110">MAPI 子系统不支持客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="0f77c-110">The MAPI subsystem does not support client fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0f77c-111">说明</span><span class="sxs-lookup"><span data-stu-id="0f77c-111">Remarks</span></span>

<span data-ttu-id="0f77c-112">若要避免从 MAPI 客户端快速关闭数据丢失，MAPI 客户端应调用基于 MAPI 子系统中返回 S_OK 结果的[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和**IMAPIClientShutdown::DoFastShutdown**方法[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中。</span><span class="sxs-lookup"><span data-stu-id="0f77c-112">To avoid data loss from the fast shutdown of a MAPI client, MAPI clients should call the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) and **IMAPIClientShutdown::DoFastShutdown** methods based on the S_OK result returned by the MAPI subsystem in the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="0f77c-113">有关详细信息，请参阅[Fast 关闭的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="0f77c-113">For more information, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0f77c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f77c-114">See also</span></span>



[<span data-ttu-id="0f77c-115">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0f77c-115">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="0f77c-116">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="0f77c-116">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

