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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 32a0051207ae34f919523fbfe3e01601b7ea5d2a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350902"
---
# <a name="imapiclientshutdowndofastshutdown"></a><span data-ttu-id="d9ae8-103">IMAPIClientShutdown::DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="d9ae8-103">IMAPIClientShutdown::DoFastShutdown</span></span>

  
  
<span data-ttu-id="d9ae8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9ae8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9ae8-105">指示 MAPI 客户端在立即退出客户端进程的意图。</span><span class="sxs-lookup"><span data-stu-id="d9ae8-105">Indicates the intention of the MAPI client to exit the client process immediately.</span></span>
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="d9ae8-106">返回值</span><span class="sxs-lookup"><span data-stu-id="d9ae8-106">Return value</span></span>

<span data-ttu-id="d9ae8-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9ae8-107">S_OK</span></span>
  
> <span data-ttu-id="d9ae8-108">mapi 子系统已向加载的 mapi 提供程序指明 mapi 客户端立即退出, 并且 mapi 提供程序已准备好进行客户端退出。</span><span class="sxs-lookup"><span data-stu-id="d9ae8-108">The MAPI subsystem has indicated to loaded MAPI providers that the MAPI client is exiting immediately, and the MAPI providers are ready for the client exit.</span></span>
    
<span data-ttu-id="d9ae8-109">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="d9ae8-109">MAPI_E_NO_SUPPORT</span></span>
  
> <span data-ttu-id="d9ae8-110">MAPI 子系统不支持客户端快速关闭。</span><span class="sxs-lookup"><span data-stu-id="d9ae8-110">The MAPI subsystem does not support client fast shutdown.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9ae8-111">注解</span><span class="sxs-lookup"><span data-stu-id="d9ae8-111">Remarks</span></span>

<span data-ttu-id="d9ae8-112">为了避免从 mapi 客户端的快速关闭中丢失数据, mapi 客户端应调用[IMAPIClientShutdown:: NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和**IMAPIClientShutdown::D**基于 MAPI 子系统返回的 S_OK 结果的 ofastshutdown 方法[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d9ae8-112">To avoid data loss from the fast shutdown of a MAPI client, MAPI clients should call the [IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) and **IMAPIClientShutdown::DoFastShutdown** methods based on the S_OK result returned by the MAPI subsystem in the [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) method.</span></span> <span data-ttu-id="d9ae8-113">有关详细信息, 请参阅[Fast Shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。</span><span class="sxs-lookup"><span data-stu-id="d9ae8-113">For more information, see [Best Practices for Fast Shutdown](best-practices-for-fast-shutdown.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9ae8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9ae8-114">See also</span></span>



[<span data-ttu-id="d9ae8-115">IMAPIClientShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d9ae8-115">IMAPIClientShutdown : IUnknown</span></span>](imapiclientshutdowniunknown.md)


[<span data-ttu-id="d9ae8-116">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="d9ae8-116">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

