---
title: SYNCSTATE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 63c47e94-f603-aef9-afed-e3819bd79408
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 080556a7ed4530bb96db20fd96d9dda86672a720
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778962"
---
# <a name="syncstate"></a><span data-ttu-id="bd2f7-103">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="bd2f7-103">SYNCSTATE</span></span>

<span data-ttu-id="bd2f7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bd2f7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bd2f7-105">此结构定义复制状态机的状态。</span><span class="sxs-lookup"><span data-stu-id="bd2f7-105">This structure defines the states for the replication state machine.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="bd2f7-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="bd2f7-106">Quick info</span></span>

```cpp
typedef enum { 
    LR_SYNC_IDLE = 0, 
    LR_SYNC, 
    LR_SYNC_UPLOAD_HIERARCHY, 
    LR_SYNC_UPLOAD_FOLDER, 
    LR_SYNC_CONTENTS, 
    LR_SYNC_UPLOAD_TABLE, 
    LR_SYNC_UPLOAD_MESSAGE, 
    LR_SYNC_UPLOAD_MESSAGE_READ = 8, 
    LR_SYNC_UPLOAD_MESSAGE_DEL, 
    LR_SYNC_DOWNLOAD_HIERARCHY, 
    LR_SYNC_DOWNLOAD_TABLE, 
    LR_SYNC_DOWNLOAD_HEADER = 17 
} SYNCSTATE; 

```

## <a name="see-also"></a><span data-ttu-id="bd2f7-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd2f7-107">See also</span></span>

- [<span data-ttu-id="bd2f7-108">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="bd2f7-108">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="bd2f7-109">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="bd2f7-109">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="bd2f7-110">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="bd2f7-110">MAPI Constants</span></span>](mapi-constants.md)

