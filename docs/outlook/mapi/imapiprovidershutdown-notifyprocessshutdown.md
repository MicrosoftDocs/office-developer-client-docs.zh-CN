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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326388"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a><span data-ttu-id="38159-103">IMAPIProviderShutdown::NotifyProcessShutdown</span><span class="sxs-lookup"><span data-stu-id="38159-103">IMAPIProviderShutdown::NotifyProcessShutdown</span></span>

  
  
<span data-ttu-id="38159-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38159-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38159-105">向 mapi 提供程序指示 mapi 客户端即将执行快速关闭, 以便提供程序可以采取措施来防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="38159-105">Indicates to the MAPI provider that a MAPI client is going to do a fast shutdown, so that the provider can take actions to prevent data loss.</span></span>
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="38159-106">返回值</span><span class="sxs-lookup"><span data-stu-id="38159-106">Return value</span></span>

<span data-ttu-id="38159-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="38159-107">S_OK</span></span>
  
> <span data-ttu-id="38159-108">mapi 提供程序在 mapi 客户端关闭时采取措施来防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="38159-108">The MAPI provider is taking actions to prevent data loss when the MAPI client shuts down.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38159-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38159-109">See also</span></span>



[<span data-ttu-id="38159-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="38159-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="38159-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="38159-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

