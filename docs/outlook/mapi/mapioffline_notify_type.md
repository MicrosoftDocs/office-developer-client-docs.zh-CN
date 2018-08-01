---
title: MAPIOFFLINE_NOTIFY_TYPE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a111d7b7-6e87-4958-8f9b-0f2adbeb8b63
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 468dfd634c4aaf18b019d06975ec9066c9d5f7a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776381"
---
# <a name="mapiofflinenotifytype"></a><span data-ttu-id="3cf9a-103">MAPIOFFLINE_NOTIFY_TYPE</span><span class="sxs-lookup"><span data-stu-id="3cf9a-103">MAPIOFFLINE_NOTIFY_TYPE</span></span>

  
  
<span data-ttu-id="3cf9a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3cf9a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cf9a-105">通知的 MAPIOFFLINE_NOTIFY_TYPE 标识如果处于连接状态更改为举行、 正在进行，或已完成。</span><span class="sxs-lookup"><span data-stu-id="3cf9a-105">The MAPIOFFLINE_NOTIFY_TYPE of a notification identifies if a change in the connection state is going to take place, is taking place, or has completed.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="3cf9a-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="3cf9a-106">Quick info</span></span>

<span data-ttu-id="3cf9a-107">请参阅**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="3cf9a-107">See **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
  
```cpp
typedef enum { 
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START = 1,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE = 2,  
    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE = 3  
} MAPIOFFLINE_NOTIFY_TYPE;
```

## <a name="see-also"></a><span data-ttu-id="3cf9a-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cf9a-108">See also</span></span>



[<span data-ttu-id="3cf9a-109">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="3cf9a-109">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="3cf9a-110">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3cf9a-110">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="3cf9a-111">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="3cf9a-111">MAPIOFFLINE_NOTIFY</span></span>](mapioffline_notify.md)

