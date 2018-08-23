---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bdfabdf02fc0fa6222418bd0fb87e9b6c17d936a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580437"
---
# <a name="uptbl"></a><span data-ttu-id="edca9-103">UPTBL</span><span class="sxs-lookup"><span data-stu-id="edca9-103">UPTBL</span></span>

<span data-ttu-id="edca9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="edca9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="edca9-105">用于[上载表状态](upload-table-state.md)期间上载文件夹的内容的信息。</span><span class="sxs-lookup"><span data-stu-id="edca9-105">Information for uploading the contents of a folder during the [upload table state](upload-table-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="edca9-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="edca9-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="edca9-107">Members</span><span class="sxs-lookup"><span data-stu-id="edca9-107">Members</span></span>

<span data-ttu-id="edca9-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="edca9-108">_ulFlags_</span></span>
  
> <span data-ttu-id="edca9-109">[in]若要在上载过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="edca9-109">[in] Flags to determine the appropriate behavior during the upload.</span></span>
    
  - <span data-ttu-id="edca9-110">UPT_OK</span><span class="sxs-lookup"><span data-stu-id="edca9-110">UPT_OK</span></span>
    
    - <span data-ttu-id="edca9-111">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="edca9-111">[in] Upload was successful.</span></span> <span data-ttu-id="edca9-112">客户端设置后将文件夹内容上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="edca9-112">The client sets this after uploading the folder contents to the server.</span></span>
    
<span data-ttu-id="edca9-113">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="edca9-113">_pstmReserved_</span></span>
  
> <span data-ttu-id="edca9-114">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="edca9-114">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="edca9-115">_pszName_</span><span class="sxs-lookup"><span data-stu-id="edca9-115">_pszName_</span></span>
  
> <span data-ttu-id="edca9-116">[输出]文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="edca9-116">[out] Name of the folder.</span></span>
    
<span data-ttu-id="edca9-117">_feid_</span><span class="sxs-lookup"><span data-stu-id="edca9-117">_feid_</span></span>
  
> <span data-ttu-id="edca9-118">[输出]文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="edca9-118">[out] Entry ID of the folder.</span></span>
    
<span data-ttu-id="edca9-119">_uintReserved_</span><span class="sxs-lookup"><span data-stu-id="edca9-119">_uintReserved_</span></span>
  
> <span data-ttu-id="edca9-120">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="edca9-120">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="edca9-121">_rgte_</span><span class="sxs-lookup"><span data-stu-id="edca9-121">_rgte_</span></span>
  
> <span data-ttu-id="edca9-122">[输出]结构的文件夹中保留的正常 （或非隐藏） 项和关联 （或隐藏） 的项的以下信息： _rgte [0]_ 是正常的项目，并且_rgte [1]_ 关联的项目。</span><span class="sxs-lookup"><span data-stu-id="edca9-122">[out] Structure to hold the following information for normal (or non-hidden) items and associated (or hidden) items in the folder:  _rgte[0]_ is for normal items, and  _rgte[1]_ is for associated items.</span></span> 
    
   - <span data-ttu-id="edca9-123">新的或修改项的数目</span><span class="sxs-lookup"><span data-stu-id="edca9-123">the number of new or modified items</span></span>
   - <span data-ttu-id="edca9-124">读取项的数目</span><span class="sxs-lookup"><span data-stu-id="edca9-124">the number of read items</span></span> 
   - <span data-ttu-id="edca9-125">已删除的项的数目</span><span class="sxs-lookup"><span data-stu-id="edca9-125">the number of deleted items</span></span>
    
 <span data-ttu-id="edca9-126">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="edca9-126">_iEnt_</span></span>
  
> <span data-ttu-id="edca9-127">[输出]要跟踪上载更改由 _%_ 指定数量的索引。</span><span class="sxs-lookup"><span data-stu-id="edca9-127">[out] Index to track uploading the number of changes specified by  _cEnt_.</span></span>
    
<span data-ttu-id="edca9-128">_%_</span><span class="sxs-lookup"><span data-stu-id="edca9-128">_cEnt_</span></span>
  
> <span data-ttu-id="edca9-129">[输出]更改应用于文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="edca9-129">[out] Number of changes to the folder.</span></span>
    
<span data-ttu-id="edca9-130">_pupmovHead_</span><span class="sxs-lookup"><span data-stu-id="edca9-130">_pupmovHead_</span></span>
  
> <span data-ttu-id="edca9-131">[输出][UPMOV](upmov.md)结构的链。</span><span class="sxs-lookup"><span data-stu-id="edca9-131">[out] Chain of [UPMOV](upmov.md) structures.</span></span> 
    
<span data-ttu-id="edca9-132">_保留_</span><span class="sxs-lookup"><span data-stu-id="edca9-132">_pReserved_</span></span>
  
> <span data-ttu-id="edca9-133">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="edca9-133">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="edca9-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edca9-134">See also</span></span>

- [<span data-ttu-id="edca9-135">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="edca9-135">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="edca9-136">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="edca9-136">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="edca9-137">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="edca9-137">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="edca9-138">UPTBLE</span><span class="sxs-lookup"><span data-stu-id="edca9-138">UPTBLE</span></span>](uptble.md)

