---
title: UPDEL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3b23291d-3355-d772-4647-d4bbd64b0b53
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 057a1ff38ed3809ce03bce8f820f1d16eea7fb46
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581123"
---
# <a name="updel"></a><span data-ttu-id="e4706-103">UPDEL</span><span class="sxs-lookup"><span data-stu-id="e4706-103">UPDEL</span></span>

  
  
<span data-ttu-id="e4706-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4706-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4706-105">已删除本地存储区中的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="e4706-105">Information for items that have been deleted in a local store.</span></span> <span data-ttu-id="e4706-106">[上载删除状态状态](upload-delete-status-state.md)期间使用此信息。</span><span class="sxs-lookup"><span data-stu-id="e4706-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e4706-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="e4706-107">Quick info</span></span>

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="e4706-108">Members</span><span class="sxs-lookup"><span data-stu-id="e4706-108">Members</span></span>

 <span data-ttu-id="e4706-109">_pupde_</span><span class="sxs-lookup"><span data-stu-id="e4706-109">_pupde_</span></span>
  
>  <span data-ttu-id="e4706-110">[输出][UPDELE](updele.md)条目的向量。</span><span class="sxs-lookup"><span data-stu-id="e4706-110">[out] Vector of [UPDELE](updele.md) entries.</span></span> 
    
 <span data-ttu-id="e4706-111">_%_</span><span class="sxs-lookup"><span data-stu-id="e4706-111">_cEnt_</span></span>
  
> <span data-ttu-id="e4706-112">[输出]*Pupde*中的条目数。</span><span class="sxs-lookup"><span data-stu-id="e4706-112">[out] Number of entries in  *pupde*  .</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e4706-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4706-113">See also</span></span>



[<span data-ttu-id="e4706-114">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="e4706-114">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e4706-115">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="e4706-115">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e4706-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e4706-116">MAPI Constants</span></span>](mapi-constants.md)

