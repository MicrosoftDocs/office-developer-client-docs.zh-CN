---
title: UPREAD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 568f2336-cb4d-3f2c-a304-d29cdb0bcbcc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 887c66277b54e2e14c7f67c76b8e9dd4fa8bc719
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589229"
---
# <a name="upread"></a><span data-ttu-id="e89a7-103">UPREAD</span><span class="sxs-lookup"><span data-stu-id="e89a7-103">UPREAD</span></span>

  
  
<span data-ttu-id="e89a7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e89a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e89a7-105">用于[上载读取状态状态](upload-read-status-state.md)期间上载读取的项的状态信息。</span><span class="sxs-lookup"><span data-stu-id="e89a7-105">Information for uploading the read state of items during the [upload read status state](upload-read-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e89a7-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="e89a7-106">Quick info</span></span>

```cpp
struct UPREAD 
{ 
    PUPREADE pupre; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="e89a7-107">Members</span><span class="sxs-lookup"><span data-stu-id="e89a7-107">Members</span></span>

 <span data-ttu-id="e89a7-108">_pupre_</span><span class="sxs-lookup"><span data-stu-id="e89a7-108">_pupre_</span></span>
  
>  <span data-ttu-id="e89a7-109">[输出]**[UPREADE](upreade.md)** 条目的向量。</span><span class="sxs-lookup"><span data-stu-id="e89a7-109">[out] Vector of **[UPREADE](upreade.md)** entries.</span></span> 
    
 <span data-ttu-id="e89a7-110">_%_</span><span class="sxs-lookup"><span data-stu-id="e89a7-110">_cEnt_</span></span>
  
>  <span data-ttu-id="e89a7-111">[输出]**UPREADE**条目数。</span><span class="sxs-lookup"><span data-stu-id="e89a7-111">[out] Number of **UPREADE** entries.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e89a7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e89a7-112">See also</span></span>



[<span data-ttu-id="e89a7-113">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="e89a7-113">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e89a7-114">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="e89a7-114">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e89a7-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e89a7-115">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="e89a7-116">UPREADE</span><span class="sxs-lookup"><span data-stu-id="e89a7-116">UPREADE</span></span>](upreade.md)

