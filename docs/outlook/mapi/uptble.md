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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413838"
---
# <a name="uptble"></a><span data-ttu-id="23f02-103">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="23f02-103">UPTBLE</span></span>

<span data-ttu-id="23f02-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23f02-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23f02-105">上传表状态期间上传文件夹 [内容的扩展信息](upload-table-state.md)。</span><span class="sxs-lookup"><span data-stu-id="23f02-105">Extended information for uploading the contents of a folder during the [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="23f02-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="23f02-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="23f02-107">成员</span><span class="sxs-lookup"><span data-stu-id="23f02-107">Members</span></span>

 <span data-ttu-id="23f02-108">_iEntMod_</span><span class="sxs-lookup"><span data-stu-id="23f02-108">_iEntMod_</span></span>
  
>  <span data-ttu-id="23f02-109">[out]跟踪新项或修改项  _的 cEntMod_ 数的上载的索引。</span><span class="sxs-lookup"><span data-stu-id="23f02-109">[out] Index to track uploading the  _cEntMod_ number of new or modified items.</span></span> 
    
 <span data-ttu-id="23f02-110">_cEntMod_</span><span class="sxs-lookup"><span data-stu-id="23f02-110">_cEntMod_</span></span>
  
>  <span data-ttu-id="23f02-111">[out]文件夹中新项或修改的项目数。</span><span class="sxs-lookup"><span data-stu-id="23f02-111">[out] Number of new or modified items in the folder.</span></span> 
    
 <span data-ttu-id="23f02-112">_iEntRead_</span><span class="sxs-lookup"><span data-stu-id="23f02-112">_iEntRead_</span></span>
  
>  <span data-ttu-id="23f02-113">[out]跟踪 cEntRead 读取项  _数的上载的_ 索引。</span><span class="sxs-lookup"><span data-stu-id="23f02-113">[out] Index to track uploading the number of  _cEntRead_ read items.</span></span> 
    
 <span data-ttu-id="23f02-114">_cEntRead_</span><span class="sxs-lookup"><span data-stu-id="23f02-114">_cEntRead_</span></span>
  
>  <span data-ttu-id="23f02-115">[out]文件夹中的读取项目数。</span><span class="sxs-lookup"><span data-stu-id="23f02-115">[out] Number of read items in the folder.</span></span> 
    
 <span data-ttu-id="23f02-116">_iEntDel_</span><span class="sxs-lookup"><span data-stu-id="23f02-116">_iEntDel_</span></span>
  
>  <span data-ttu-id="23f02-117">[out]跟踪  _cEntDel_ 已删除项目数的上载的索引。</span><span class="sxs-lookup"><span data-stu-id="23f02-117">[out] Index to track uploading the number of  _cEntDel_ deleted items.</span></span> 
    
 <span data-ttu-id="23f02-118">_cEntDel_</span><span class="sxs-lookup"><span data-stu-id="23f02-118">_cEntDel_</span></span>
  
>  <span data-ttu-id="23f02-119">[out]文件夹中已删除项目的数量。</span><span class="sxs-lookup"><span data-stu-id="23f02-119">[out] Number of deleted items in the folder.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="23f02-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23f02-120">See also</span></span>

- [<span data-ttu-id="23f02-121">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="23f02-121">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="23f02-122">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="23f02-122">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="23f02-123">UPTBL</span><span class="sxs-lookup"><span data-stu-id="23f02-123">UPTBL</span></span>](uptbl.md)

