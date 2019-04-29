---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b401f54df020fb6553cbdcc5b85206ee422a8429
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438111"
---
# <a name="uptbl"></a><span data-ttu-id="0c6e8-103">UPTBL</span><span class="sxs-lookup"><span data-stu-id="0c6e8-103">UPTBL</span></span>

<span data-ttu-id="0c6e8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c6e8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c6e8-105">[上载表状态](upload-table-state.md)期间上载文件夹内容的信息。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-105">Information for uploading the contents of a folder during the [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0c6e8-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="0c6e8-106">Quick info</span></span>

```cpp
struct UPTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    LPSTR pszName; 
    FEID feid; 
    UINT uintReserved; 
    UPTBLE rgte[2]; 
    UINT iEnt; 
    UINT cEnt; 
    PUPMOV pupmovHead; 
    void* pReserved; 
};
```

## <a name="members"></a><span data-ttu-id="0c6e8-107">成员</span><span class="sxs-lookup"><span data-stu-id="0c6e8-107">Members</span></span>

<span data-ttu-id="0c6e8-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-108">_ulFlags_</span></span>
  
> <span data-ttu-id="0c6e8-109">实时用于在上载过程中确定相应行为的标志。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-109">[in] Flags to determine the appropriate behavior during the upload.</span></span>
    
  - <span data-ttu-id="0c6e8-110">UPT_OK</span><span class="sxs-lookup"><span data-stu-id="0c6e8-110">UPT_OK</span></span>
    
    - <span data-ttu-id="0c6e8-111">实时上载成功。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-111">[in] Upload was successful.</span></span> <span data-ttu-id="0c6e8-112">客户端将文件夹内容上载到服务器后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-112">The client sets this after uploading the folder contents to the server.</span></span>
    
<span data-ttu-id="0c6e8-113">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-113">_pstmReserved_</span></span>
  
> <span data-ttu-id="0c6e8-114">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-114">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="0c6e8-115">_pszName_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-115">_pszName_</span></span>
  
> <span data-ttu-id="0c6e8-116">[传出] 文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-116">[out] Name of the folder.</span></span>
    
<span data-ttu-id="0c6e8-117">_feid_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-117">_feid_</span></span>
  
> <span data-ttu-id="0c6e8-118">[传出] 文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-118">[out] Entry ID of the folder.</span></span>
    
<span data-ttu-id="0c6e8-119">_uintReserved_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-119">_uintReserved_</span></span>
  
> <span data-ttu-id="0c6e8-120">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-120">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="0c6e8-121">_rgte_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-121">_rgte_</span></span>
  
> <span data-ttu-id="0c6e8-122">排除用于保存文件夹中的普通 (或非隐藏) 项目以及关联 (或隐藏) 项目的以下信息的结构: _rgte [0]_ 适用于普通项目, 而_rgte [1]_ 用于关联的项目。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-122">[out] Structure to hold the following information for normal (or non-hidden) items and associated (or hidden) items in the folder:  _rgte[0]_ is for normal items, and  _rgte[1]_ is for associated items.</span></span> 
    
   - <span data-ttu-id="0c6e8-123">新项目或修改的项目的数量</span><span class="sxs-lookup"><span data-stu-id="0c6e8-123">the number of new or modified items</span></span>
   - <span data-ttu-id="0c6e8-124">读取项目数</span><span class="sxs-lookup"><span data-stu-id="0c6e8-124">the number of read items</span></span> 
   - <span data-ttu-id="0c6e8-125">已删除项目的数量</span><span class="sxs-lookup"><span data-stu-id="0c6e8-125">the number of deleted items</span></span>
    
 <span data-ttu-id="0c6e8-126">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-126">_iEnt_</span></span>
  
> <span data-ttu-id="0c6e8-127">排除用于跟踪上传由_分币_指定的更改数的索引。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-127">[out] Index to track uploading the number of changes specified by  _cEnt_.</span></span>
    
<span data-ttu-id="0c6e8-128">_分币_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-128">_cEnt_</span></span>
  
> <span data-ttu-id="0c6e8-129">排除对文件夹所做的更改的数量。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-129">[out] Number of changes to the folder.</span></span>
    
<span data-ttu-id="0c6e8-130">_pupmovHead_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-130">_pupmovHead_</span></span>
  
> <span data-ttu-id="0c6e8-131">排除[UPMOV](upmov.md)结构的链。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-131">[out] Chain of [UPMOV](upmov.md) structures.</span></span> 
    
<span data-ttu-id="0c6e8-132">_保护_</span><span class="sxs-lookup"><span data-stu-id="0c6e8-132">_pReserved_</span></span>
  
> <span data-ttu-id="0c6e8-133">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="0c6e8-133">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c6e8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c6e8-134">See also</span></span>

- [<span data-ttu-id="0c6e8-135">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="0c6e8-135">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="0c6e8-136">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="0c6e8-136">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="0c6e8-137">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="0c6e8-137">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="0c6e8-138">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="0c6e8-138">UPTBLE</span></span>](uptble.md)

