---
title: UPDEL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3b23291d-3355-d772-4647-d4bbd64b0b53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c9d2ec7f1970e3d1cadb65ab9af360b5c01c6844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436796"
---
# <a name="updel"></a><span data-ttu-id="97bbc-103">UPDEL</span><span class="sxs-lookup"><span data-stu-id="97bbc-103">UPDEL</span></span>

  
  
<span data-ttu-id="97bbc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97bbc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97bbc-105">已在本地存储区中删除的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="97bbc-105">Information for items that have been deleted in a local store.</span></span> <span data-ttu-id="97bbc-106">此信息在[上载删除状态状态](upload-delete-status-state.md)期间使用。</span><span class="sxs-lookup"><span data-stu-id="97bbc-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="97bbc-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="97bbc-107">Quick info</span></span>

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="97bbc-108">成员</span><span class="sxs-lookup"><span data-stu-id="97bbc-108">Members</span></span>

 <span data-ttu-id="97bbc-109">_pupde_</span><span class="sxs-lookup"><span data-stu-id="97bbc-109">_pupde_</span></span>
  
>  <span data-ttu-id="97bbc-110">排除[UPDELE](updele.md)条目的矢量。</span><span class="sxs-lookup"><span data-stu-id="97bbc-110">[out] Vector of [UPDELE](updele.md) entries.</span></span> 
    
 <span data-ttu-id="97bbc-111">_分币_</span><span class="sxs-lookup"><span data-stu-id="97bbc-111">_cEnt_</span></span>
  
> <span data-ttu-id="97bbc-112">排除*pupde*中的条目数。</span><span class="sxs-lookup"><span data-stu-id="97bbc-112">[out] Number of entries in  *pupde*  .</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="97bbc-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97bbc-113">See also</span></span>



[<span data-ttu-id="97bbc-114">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="97bbc-114">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="97bbc-115">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="97bbc-115">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="97bbc-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="97bbc-116">MAPI Constants</span></span>](mapi-constants.md)

