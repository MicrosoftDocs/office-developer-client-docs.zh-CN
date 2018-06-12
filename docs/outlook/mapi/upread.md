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
ms.openlocfilehash: fa3c0b90a64c90a7c854cb22ac75438fa5fca23f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779057"
---
# <a name="upread"></a><span data-ttu-id="e3044-103">UPREAD</span><span class="sxs-lookup"><span data-stu-id="e3044-103">UPREAD</span></span>

  
  
<span data-ttu-id="e3044-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e3044-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e3044-105">用于[上载读取状态状态](upload-read-status-state.md)期间上载读取的项的状态信息。</span><span class="sxs-lookup"><span data-stu-id="e3044-105">Information for uploading the read state of items during the [upload read status state](upload-read-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e3044-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="e3044-106">Quick info</span></span>

```cpp
struct UPREAD 
{ 
    PUPREADE pupre; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="e3044-107">成员</span><span class="sxs-lookup"><span data-stu-id="e3044-107">Members</span></span>

 <span data-ttu-id="e3044-108">_pupre_</span><span class="sxs-lookup"><span data-stu-id="e3044-108">_pupre_</span></span>
  
>  <span data-ttu-id="e3044-109">[输出]**[UPREADE](upreade.md)** 条目的向量。</span><span class="sxs-lookup"><span data-stu-id="e3044-109">[out] Vector of **[UPREADE](upreade.md)** entries.</span></span> 
    
 <span data-ttu-id="e3044-110">_%_</span><span class="sxs-lookup"><span data-stu-id="e3044-110">_cEnt_</span></span>
  
>  <span data-ttu-id="e3044-111">[输出]**UPREADE**条目数。</span><span class="sxs-lookup"><span data-stu-id="e3044-111">[out] Number of **UPREADE** entries.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e3044-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3044-112">See also</span></span>



[<span data-ttu-id="e3044-113">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="e3044-113">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e3044-114">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="e3044-114">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e3044-115">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e3044-115">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="e3044-116">UPREADE</span><span class="sxs-lookup"><span data-stu-id="e3044-116">UPREADE</span></span>](upreade.md)

