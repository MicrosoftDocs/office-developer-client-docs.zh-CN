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
ms.openlocfilehash: 9495caecd514656f6fd62fb5db6cd8ac2faf4b50
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581739"
---
# <a name="indexsearchpusherprocess"></a><span data-ttu-id="0fd51-103">INDEX_SEARCH_PUSHER_PROCESS</span><span class="sxs-lookup"><span data-stu-id="0fd51-103">INDEX_SEARCH_PUSHER_PROCESS</span></span>

  
  
<span data-ttu-id="0fd51-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0fd51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0fd51-105">指定发送通知到 MAPI 协议处理程序中存储的对象可供索引的进程。</span><span class="sxs-lookup"><span data-stu-id="0fd51-105">Specifies the process that is sending a notification to the MAPI Protocol Handler that an object in that store is ready for indexing.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0fd51-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="0fd51-106">Quick info</span></span>

```cpp
typedef struct _INDEX_SEARCH_PUSHER_PROCESS {  
    DWORD dwPID;  
} INDEX_SEARCH_PUSHER_PROCESS; 
```

## <a name="members"></a><span data-ttu-id="0fd51-107">Members</span><span class="sxs-lookup"><span data-stu-id="0fd51-107">Members</span></span>

 <span data-ttu-id="0fd51-108">*dwPID*</span><span class="sxs-lookup"><span data-stu-id="0fd51-108">*dwPID*</span></span> 
  
>  <span data-ttu-id="0fd51-109">正在向索引通知发送到索引器的 MAPI 协议处理程序的过程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="0fd51-109">Process ID for the process that is sending an indexing notification to the indexer of the MAPI Protocol Handler.</span></span> 
    

