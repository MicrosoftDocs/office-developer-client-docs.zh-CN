---
title: IMAPIClientShutdownNotifyProcessShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.NotifyProcessShutdown
api_type:
- COM
ms.assetid: 42dd7889-5e00-419a-91e7-8350be4efd35
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 04a9b631c3a4f33282bce44e06d92e089349c76b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775307"
---
# <a name="imapiclientshutdownnotifyprocessshutdown"></a><span data-ttu-id="0e8be-103">IMAPIClientShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="0e8be-103">IMAPIClientShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="0e8be-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0e8be-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0e8be-105">表示的 MAPI 客户端的目的，继续执行关闭。</span><span class="sxs-lookup"><span data-stu-id="0e8be-105">Indicates the intention of the MAPI client to proceed with shut down.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="0e8be-106">返回值</span><span class="sxs-lookup"><span data-stu-id="0e8be-106">Return value</span></span>

<span data-ttu-id="0e8be-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e8be-107">S_OK</span></span>
  
> <span data-ttu-id="0e8be-108">MAPI 子系统试图通知 MAPI 客户端正在进行快速关闭加载的 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0e8be-108">The MAPI subsystem has attempted to notify loaded MAPI providers that the MAPI client is going to do a fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0e8be-109">说明</span><span class="sxs-lookup"><span data-stu-id="0e8be-109">Remarks</span></span>

<span data-ttu-id="0e8be-110">若要避免从 MAPI 客户端快速关闭数据丢失，MAPI 客户端应调用基于 MAPI 子系统中返回 S_OK 结果的**IMAPIClientShutdown::NotifyProcessShutdown**和[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中。</span><span class="sxs-lookup"><span data-stu-id="0e8be-110">To avoid data loss from the fast shutdown of a MAPI client, MAPI clients should call the **IMAPIClientShutdown::NotifyProcessShutdown** and [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) methods based on the S_OK result returned by the MAPI subsystem in the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="0e8be-111">有关详细信息，请参阅[Fast 关闭的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="0e8be-111">For more information, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e8be-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e8be-112">See also</span></span>



[<span data-ttu-id="0e8be-113">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0e8be-113">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="0e8be-114">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="0e8be-114">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

