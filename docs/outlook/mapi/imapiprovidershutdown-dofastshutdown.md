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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4ff93ed9353d58ef6b68823bebf8b5b27a0df6e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322419"
---
# <a name="imapiprovidershutdowndofastshutdown"></a><span data-ttu-id="c7608-103">IMAPIProviderShutdown::DoFastShutdown</span><span class="sxs-lookup"><span data-stu-id="c7608-103">IMAPIProviderShutdown::DoFastShutdown</span></span>

  
  
<span data-ttu-id="c7608-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7608-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7608-105">向 mapi 提供程序指示 mapi 客户端立即退出, 以便 mapi 提供程序将保留所做的更改以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="c7608-105">Indicates to the MAPI provider that the MAPI client is exiting immediately, so that the MAPI provider will persist changes to prevent data loss.</span></span>
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a><span data-ttu-id="c7608-106">返回值</span><span class="sxs-lookup"><span data-stu-id="c7608-106">Return value</span></span>

<span data-ttu-id="c7608-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7608-107">S_OK</span></span>
  
> <span data-ttu-id="c7608-108">mapi 提供程序已准备好, 可立即退出 mapi 客户端。</span><span class="sxs-lookup"><span data-stu-id="c7608-108">The MAPI provider is ready for the MAPI client to exit immediately.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="c7608-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7608-109">See also</span></span>



[<span data-ttu-id="c7608-110">IMAPIProviderShutdown : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c7608-110">IMAPIProviderShutdown : IUnknown</span></span>](imapiprovidershutdowniunknown.md)


[<span data-ttu-id="c7608-111">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="c7608-111">Client Shutdown in MAPI</span></span>](client-shutdown-in-mapi.md)

