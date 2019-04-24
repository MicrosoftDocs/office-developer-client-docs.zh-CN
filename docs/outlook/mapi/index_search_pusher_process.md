---
title: INDEX_SEARCH_PUSHER_PROCESS
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6b39504f-6eed-2605-048d-2707f38a7d9a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 64e5cf31dffdc794a22bcbd6d503a2b688f9c733
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332205"
---
# <a name="indexsearchpusherprocess"></a><span data-ttu-id="c39f3-103">INDEX_SEARCH_PUSHER_PROCESS</span><span class="sxs-lookup"><span data-stu-id="c39f3-103">INDEX_SEARCH_PUSHER_PROCESS</span></span>

  
  
<span data-ttu-id="c39f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c39f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c39f3-105">指定向 MAPI 协议处理程序发送通知的过程, 该存储区中的对象已准备好编制索引。</span><span class="sxs-lookup"><span data-stu-id="c39f3-105">Specifies the process that is sending a notification to the MAPI Protocol Handler that an object in that store is ready for indexing.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="c39f3-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="c39f3-106">Quick info</span></span>

```cpp
typedef struct _INDEX_SEARCH_PUSHER_PROCESS {  
    DWORD dwPID;  
} INDEX_SEARCH_PUSHER_PROCESS; 
```

## <a name="members"></a><span data-ttu-id="c39f3-107">成员</span><span class="sxs-lookup"><span data-stu-id="c39f3-107">Members</span></span>

 <span data-ttu-id="c39f3-108">*dwPID*</span><span class="sxs-lookup"><span data-stu-id="c39f3-108">*dwPID*</span></span> 
  
>  <span data-ttu-id="c39f3-109">将索引通知发送给 MAPI 协议处理程序索引器的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="c39f3-109">Process ID for the process that is sending an indexing notification to the indexer of the MAPI Protocol Handler.</span></span> 
    

