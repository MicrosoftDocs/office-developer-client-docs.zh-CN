---
title: INDEX_SEARCH_PUSHER_PROCESS
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6b39504f-6eed-2605-048d-2707f38a7d9a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ada6d4127d503aae0b068d40d2bb48cb6b833ea0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775928"
---
# <a name="indexsearchpusherprocess"></a><span data-ttu-id="2c227-103">INDEX_SEARCH_PUSHER_PROCESS</span><span class="sxs-lookup"><span data-stu-id="2c227-103">INDEX_SEARCH_PUSHER_PROCESS</span></span>

  
  
<span data-ttu-id="2c227-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2c227-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2c227-105">指定发送通知到 MAPI 协议处理程序中存储的对象可供索引的进程。</span><span class="sxs-lookup"><span data-stu-id="2c227-105">Specifies the process that is sending a notification to the MAPI Protocol Handler that an object in that store is ready for indexing.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2c227-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="2c227-106">Quick info</span></span>

```cpp
typedef struct _INDEX_SEARCH_PUSHER_PROCESS {  
    DWORD dwPID;  
} INDEX_SEARCH_PUSHER_PROCESS; 
```

## <a name="members"></a><span data-ttu-id="2c227-107">Members</span><span class="sxs-lookup"><span data-stu-id="2c227-107">Members</span></span>

 <span data-ttu-id="2c227-108">*dwPID*</span><span class="sxs-lookup"><span data-stu-id="2c227-108">*dwPID*</span></span> 
  
>  <span data-ttu-id="2c227-109">正在向索引通知发送到索引器的 MAPI 协议处理程序的过程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="2c227-109">Process ID for the process that is sending an indexing notification to the indexer of the MAPI Protocol Handler.</span></span> 
    

