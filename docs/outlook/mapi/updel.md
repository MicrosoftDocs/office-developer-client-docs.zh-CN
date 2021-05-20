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
# <a name="updel"></a><span data-ttu-id="78ad4-103">UPDEL</span><span class="sxs-lookup"><span data-stu-id="78ad4-103">UPDEL</span></span>

  
  
<span data-ttu-id="78ad4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="78ad4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="78ad4-105">本地存储中已删除的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="78ad4-105">Information for items that have been deleted in a local store.</span></span> <span data-ttu-id="78ad4-106">此信息在上载删除 [状态期间使用](upload-delete-status-state.md)。</span><span class="sxs-lookup"><span data-stu-id="78ad4-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="78ad4-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="78ad4-107">Quick info</span></span>

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a><span data-ttu-id="78ad4-108">成员</span><span class="sxs-lookup"><span data-stu-id="78ad4-108">Members</span></span>

 <span data-ttu-id="78ad4-109">_pupde_</span><span class="sxs-lookup"><span data-stu-id="78ad4-109">_pupde_</span></span>
  
>  <span data-ttu-id="78ad4-110">[out] [UPDELE 条目](updele.md) 的矢量。</span><span class="sxs-lookup"><span data-stu-id="78ad4-110">[out] Vector of [UPDELE](updele.md) entries.</span></span> 
    
 <span data-ttu-id="78ad4-111">_cEnt_</span><span class="sxs-lookup"><span data-stu-id="78ad4-111">_cEnt_</span></span>
  
> <span data-ttu-id="78ad4-112">[out]  *pupde 中的条目数*  。</span><span class="sxs-lookup"><span data-stu-id="78ad4-112">[out] Number of entries in  *pupde*  .</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="78ad4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78ad4-113">See also</span></span>



[<span data-ttu-id="78ad4-114">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="78ad4-114">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="78ad4-115">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="78ad4-115">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="78ad4-116">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="78ad4-116">MAPI Constants</span></span>](mapi-constants.md)

