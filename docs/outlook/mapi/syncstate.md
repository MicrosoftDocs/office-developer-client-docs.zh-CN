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
ms.openlocfilehash: a27f38e759862c7091205a6f9a8aa1cde90c38e3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575530"
---
# <a name="syncstate"></a><span data-ttu-id="512b5-103">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="512b5-103">SYNCSTATE</span></span>

<span data-ttu-id="512b5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="512b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="512b5-105">此结构定义复制状态机的状态。</span><span class="sxs-lookup"><span data-stu-id="512b5-105">This structure defines the states for the replication state machine.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="512b5-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="512b5-106">Quick info</span></span>

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

## <a name="see-also"></a><span data-ttu-id="512b5-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="512b5-107">See also</span></span>

- [<span data-ttu-id="512b5-108">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="512b5-108">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="512b5-109">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="512b5-109">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="512b5-110">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="512b5-110">MAPI Constants</span></span>](mapi-constants.md)

