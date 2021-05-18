---
title: IMAPIProviderShutdownNotifyProcessShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.NotifyProcessShutdown
api_type:
- COM
ms.assetid: a00d71b1-d705-40d5-b667-f91b57db85da
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b18cfc2191ffee936e1056d9bb656a7ad7dd3ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405245"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a><span data-ttu-id="b3f0d-103">IMAPIProviderShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="b3f0d-103">IMAPIProviderShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="b3f0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3f0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3f0d-105">向 MAPI 提供程序指示 MAPI 客户端将快速关闭，以便提供程序可以采取措施防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b3f0d-105">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="b3f0d-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b3f0d-106">Return value</span></span>

<span data-ttu-id="b3f0d-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3f0d-107">S_OK</span></span>
  
> <span data-ttu-id="b3f0d-108">MAPI 提供程序正在采取措施防止在 MAPI 客户端关闭时丢失数据。</span><span class="sxs-lookup"><span data-stu-id="b3f0d-108">The MAPI provider is taking actions to prevent data loss when the MAPI client shuts down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3f0d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f0d-109">See also</span></span>



[<span data-ttu-id="b3f0d-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b3f0d-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="b3f0d-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="b3f0d-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

