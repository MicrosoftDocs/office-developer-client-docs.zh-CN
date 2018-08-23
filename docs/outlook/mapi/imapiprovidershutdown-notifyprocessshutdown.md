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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 251359a98f89c88e707e4f705bd94b1f30b32cbd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592050"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a><span data-ttu-id="b26ea-103">IMAPIProviderShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="b26ea-103">IMAPIProviderShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="b26ea-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b26ea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b26ea-105">表示的 MAPI 提供程序，MAPI 客户端将要执行快速关闭，以便提供程序可以执行操作，以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b26ea-105">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="b26ea-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b26ea-106">Return value</span></span>

<span data-ttu-id="b26ea-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="b26ea-107">S_OK</span></span>
  
> <span data-ttu-id="b26ea-108">MAPI 提供程序采取操作来 MAPI 客户端关闭时防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b26ea-108">The MAPI provider is taking actions to prevent data loss when the MAPI client shuts down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b26ea-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b26ea-109">See also</span></span>



[<span data-ttu-id="b26ea-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b26ea-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="b26ea-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="b26ea-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

