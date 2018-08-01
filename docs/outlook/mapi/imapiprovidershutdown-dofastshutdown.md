---
title: IMAPIProviderShutdownDoFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.DoFastShutdown
api_type:
- COM
ms.assetid: d2b66a8e-2e28-4c32-af95-38d345c7bbd7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7c38f0650315495875357862f5fa7fe138d2c61b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775523"
---
# <a name="imapiprovidershutdowndofastshutdown"></a><span data-ttu-id="b19f9-103">IMAPIProviderShutdown::DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="b19f9-103">IMAPIProviderShutdown::DoFastShutdown</span></span>

  
  
<span data-ttu-id="b19f9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b19f9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b19f9-105">指示到 MAPI 提供程序 MAPI 客户端立即退出以便 MAPI 提供程序将保留更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b19f9-105">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="b19f9-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b19f9-106">Return value</span></span>

<span data-ttu-id="b19f9-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="b19f9-107">S_OK</span></span>
  
> <span data-ttu-id="b19f9-108">准备立即退出 MAPI 客户端的 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b19f9-108">The MAPI provider is ready for the MAPI client to exit immediately.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b19f9-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b19f9-109">See also</span></span>



[<span data-ttu-id="b19f9-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b19f9-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="b19f9-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="b19f9-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

