---
title: SYNCSTATE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 63c47e94-f603-aef9-afed-e3819bd79408
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 64348347ea930e6a6a80b9a9075299d2e3109eda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360702"
---
# <a name="syncstate"></a><span data-ttu-id="6022e-103">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="6022e-103">SYNCSTATE</span></span>

<span data-ttu-id="6022e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6022e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6022e-105">此结构定义复制状态机的状态。</span><span class="sxs-lookup"><span data-stu-id="6022e-105">This structure defines the states for the replication state machine.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6022e-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6022e-106">Quick info</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6022e-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6022e-107">See also</span></span>

- [<span data-ttu-id="6022e-108">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="6022e-108">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="6022e-109">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="6022e-109">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="6022e-110">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6022e-110">MAPI Constants</span></span>](mapi-constants.md)

