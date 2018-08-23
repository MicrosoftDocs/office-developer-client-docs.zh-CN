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
ms.openlocfilehash: faa061ae323dd744d12e4f9abec713c71379feba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563469"
---
# <a name="imapiprovidershutdowndofastshutdown"></a><span data-ttu-id="50e51-103">IMAPIProviderShutdown::DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="50e51-103">IMAPIProviderShutdown::DoFastShutdown</span></span>

  
  
<span data-ttu-id="50e51-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50e51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50e51-105">指示到 MAPI 提供程序 MAPI 客户端立即退出以便 MAPI 提供程序将保留更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="50e51-105">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="50e51-106">返回值</span><span class="sxs-lookup"><span data-stu-id="50e51-106">Return value</span></span>

<span data-ttu-id="50e51-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="50e51-107">S_OK</span></span>
  
> <span data-ttu-id="50e51-108">准备立即退出 MAPI 客户端的 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="50e51-108">The MAPI provider is ready for the MAPI client to exit immediately.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="50e51-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50e51-109">See also</span></span>



[<span data-ttu-id="50e51-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="50e51-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="50e51-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="50e51-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

