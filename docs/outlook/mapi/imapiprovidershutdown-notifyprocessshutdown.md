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
ms.openlocfilehash: cce98dc630dd9f7fa459ca31d94d012ba9a7fd85
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775544"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a><span data-ttu-id="46fd1-103">IMAPIProviderShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="46fd1-103">IMAPIProviderShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="46fd1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="46fd1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="46fd1-105">表示的 MAPI 提供程序，MAPI 客户端将要执行快速关闭，以便提供程序可以执行操作，以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="46fd1-105">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="46fd1-106">返回值</span><span class="sxs-lookup"><span data-stu-id="46fd1-106">Return value</span></span>

<span data-ttu-id="46fd1-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="46fd1-107">S_OK</span></span>
  
> <span data-ttu-id="46fd1-108">MAPI 提供程序采取操作来 MAPI 客户端关闭时防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="46fd1-108">The MAPI provider is taking actions to prevent data loss when the MAPI client shuts down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="46fd1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46fd1-109">See also</span></span>



[<span data-ttu-id="46fd1-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="46fd1-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="46fd1-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="46fd1-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

