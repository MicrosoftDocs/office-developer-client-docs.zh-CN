---
title: MAPIOFFLINE_NOTIFY_TYPE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a111d7b7-6e87-4958-8f9b-0f2adbeb8b63
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 65ed848907e196c315e8ddb61c4afd2fe03faa18
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413428"
---
# <a name="mapiofflinenotifytype"></a><span data-ttu-id="9586d-103">MAPIOFFLINE_NOTIFY_TYPE</span><span class="sxs-lookup"><span data-stu-id="9586d-103">MAPIOFFLINE_NOTIFY_TYPE</span></span>

  
  
<span data-ttu-id="9586d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9586d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9586d-105">通知的 MAPIOFFLINE_NOTIFY_TYPE, 用于标识连接状态中发生的更改是正在发生, 还是已完成。</span><span class="sxs-lookup"><span data-stu-id="9586d-105">The MAPIOFFLINE_NOTIFY_TYPE of a notification identifies if a change in the connection state is going to take place, is taking place, or has completed.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="9586d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="9586d-106">Quick info</span></span>

<span data-ttu-id="9586d-107">请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="9586d-107">See **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
  
```cpp
typedef enum { 
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START = 1,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE = 2,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE = 3  
} MAPIOFFLINE_NOTIFY_TYPE;
```

## <a name="see-also"></a><span data-ttu-id="9586d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9586d-108">See also</span></span>



[<span data-ttu-id="9586d-109">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="9586d-109">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="9586d-110">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="9586d-110">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="9586d-111">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="9586d-111">MAPIOFFLINE_NOTIFY</span></span>](mapioffline_notify.md)

