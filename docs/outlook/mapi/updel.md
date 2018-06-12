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
ms.openlocfilehash: bfc03f7fe573005a235154cf179dcf44bf4abd65
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779040"
---
# <a name="updel"></a><span data-ttu-id="902f1-103">UPDEL</span><span class="sxs-lookup"><span data-stu-id="902f1-103">UPDEL</span></span>

  
  
<span data-ttu-id="902f1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="902f1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="902f1-105">已删除本地存储区中的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="902f1-105">Information for items that have been deleted in a local store.</span></span> <span data-ttu-id="902f1-106">[上载删除状态状态](upload-delete-status-state.md)期间使用此信息。</span><span class="sxs-lookup"><span data-stu-id="902f1-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="902f1-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="902f1-107">Quick info</span></span>

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="902f1-108">成员</span><span class="sxs-lookup"><span data-stu-id="902f1-108">Members</span></span>

 <span data-ttu-id="902f1-109">_pupde_</span><span class="sxs-lookup"><span data-stu-id="902f1-109">_pupde_</span></span>
  
>  <span data-ttu-id="902f1-110">[输出][UPDELE](updele.md)条目的向量。</span><span class="sxs-lookup"><span data-stu-id="902f1-110">[out] Vector of [UPDELE](updele.md) entries.</span></span> 
    
 <span data-ttu-id="902f1-111">_%_</span><span class="sxs-lookup"><span data-stu-id="902f1-111">_cEnt_</span></span>
  
> <span data-ttu-id="902f1-112">[输出]*Pupde*中的条目数。</span><span class="sxs-lookup"><span data-stu-id="902f1-112">[out] Number of entries in  *pupde*  .</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="902f1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="902f1-113">See also</span></span>



[<span data-ttu-id="902f1-114">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="902f1-114">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="902f1-115">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="902f1-115">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="902f1-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="902f1-116">MAPI Constants</span></span>](mapi-constants.md)

