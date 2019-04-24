---
title: UPTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f7fcb385-186d-d5fe-7104-fe0af09d5768
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0b440f01aad7078ed76cd37d36c5ad506215438
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329706"
---
# <a name="uptble"></a><span data-ttu-id="7b8d0-103">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="7b8d0-103">UPTBLE</span></span>

<span data-ttu-id="7b8d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b8d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b8d0-105">[上载表状态](upload-table-state.md)期间上载文件夹内容的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-105">Extended information for uploading the contents of a folder during the [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7b8d0-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7b8d0-106">Quick info</span></span>

```cpp
struct UPTBLE 
{ 
    UINTiEntMod; 
    UINTcEntMod; 
    UINTiEntRead; 
    UINTcEntRead; 
    UINTiEntDel; 
    UINTcEntDel; 
};
```

## <a name="members"></a><span data-ttu-id="7b8d0-107">成员</span><span class="sxs-lookup"><span data-stu-id="7b8d0-107">Members</span></span>

 <span data-ttu-id="7b8d0-108">_iEntMod_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-108">_iEntMod_</span></span>
  
>  <span data-ttu-id="7b8d0-109">排除用于跟踪上载新项目或修改的项目的_cEntMod_数量的索引。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-109">[out] Index to track uploading the  _cEntMod_ number of new or modified items.</span></span> 
    
 <span data-ttu-id="7b8d0-110">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-110">_cEntMod_</span></span>
  
>  <span data-ttu-id="7b8d0-111">排除文件夹中新项目或修改项目的数量。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-111">[out] Number of new or modified items in the folder.</span></span> 
    
 <span data-ttu-id="7b8d0-112">_iEntRead_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-112">_iEntRead_</span></span>
  
>  <span data-ttu-id="7b8d0-113">排除用于跟踪上载_cEntRead_读取项目数的索引。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-113">[out] Index to track uploading the number of  _cEntRead_ read items.</span></span> 
    
 <span data-ttu-id="7b8d0-114">_cEntRead_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-114">_cEntRead_</span></span>
  
>  <span data-ttu-id="7b8d0-115">排除文件夹中的已读项目数。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-115">[out] Number of read items in the folder.</span></span> 
    
 <span data-ttu-id="7b8d0-116">_iEntDel_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-116">_iEntDel_</span></span>
  
>  <span data-ttu-id="7b8d0-117">排除用于跟踪上载_cEntDel_已删除项目数的索引。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-117">[out] Index to track uploading the number of  _cEntDel_ deleted items.</span></span> 
    
 <span data-ttu-id="7b8d0-118">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="7b8d0-118">_cEntDel_</span></span>
  
>  <span data-ttu-id="7b8d0-119">排除文件夹中已删除项目的数量。</span><span class="sxs-lookup"><span data-stu-id="7b8d0-119">[out] Number of deleted items in the folder.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7b8d0-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b8d0-120">See also</span></span>

- [<span data-ttu-id="7b8d0-121">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="7b8d0-121">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="7b8d0-122">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="7b8d0-122">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="7b8d0-123">UPTBL</span><span class="sxs-lookup"><span data-stu-id="7b8d0-123">UPTBL</span></span>](uptbl.md)

