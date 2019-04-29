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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6eef3047368caca5bd932e19738b1d996c3ff28a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438867"
---
# <a name="imapiclientshutdownnotifyprocessshutdown"></a><span data-ttu-id="8ff0c-103">IMAPIClientShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="8ff0c-103">IMAPIClientShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="8ff0c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8ff0c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8ff0c-105">指示 MAPI 客户端的意向继续关闭。</span><span class="sxs-lookup"><span data-stu-id="8ff0c-105">Indicates the intention of the MAPI client to proceed with shut down.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="8ff0c-106">返回值</span><span class="sxs-lookup"><span data-stu-id="8ff0c-106">Return value</span></span>

<span data-ttu-id="8ff0c-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ff0c-107">S_OK</span></span>
  
> <span data-ttu-id="8ff0c-108">mapi 子系统已尝试通知加载的 mapi 提供程序, mapi 客户端即将执行快速关闭。</span><span class="sxs-lookup"><span data-stu-id="8ff0c-108">The MAPI subsystem has attempted to notify loaded MAPI providers that the MAPI client is going to do a fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8ff0c-109">说明</span><span class="sxs-lookup"><span data-stu-id="8ff0c-109">Remarks</span></span>

<span data-ttu-id="8ff0c-110">为了避免从 mapi 客户端的快速关闭中丢失数据, mapi 客户端应调用**IMAPIClientShutdown:: NotifyProcessShutdown**和[IMAPIClientShutdown::D](imapiclientshutdown-dofastshutdown.md)基于 MAPI 子系统返回的 S_OK 结果的 ofastshutdown 方法[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8ff0c-110">To avoid data loss from the fast shutdown of a MAPI client, MAPI clients should call the **IMAPIClientShutdown::NotifyProcessShutdown** and [IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md) methods based on the S_OK result returned by the MAPI subsystem in the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="8ff0c-111">有关详细信息, 请参阅[Fast Shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff0c-111">For more information, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ff0c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff0c-112">See also</span></span>



[<span data-ttu-id="8ff0c-113">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8ff0c-113">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="8ff0c-114">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="8ff0c-114">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

