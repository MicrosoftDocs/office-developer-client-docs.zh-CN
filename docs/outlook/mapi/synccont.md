---
title: SYNCCONT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7b4307a3-5a8c-89bf-1113-2549556a7fe7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82923895353cf600c4d0b78b9a6e16fc7d57e466
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778927"
---
# <a name="synccont"></a><span data-ttu-id="8362b-103">SYNCCONT</span><span class="sxs-lookup"><span data-stu-id="8362b-103">SYNCCONT</span></span>

<span data-ttu-id="8362b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8362b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8362b-105">将本地存储区中的指定文件夹的内容与服务器同步过程中[同步内容状态](synchronize-contents-state.md)信息。</span><span class="sxs-lookup"><span data-stu-id="8362b-105">Information for synchronizing the contents of specified folders in a local store with the server during the [synchronize contents state](synchronize-contents-state.md).</span></span> <span data-ttu-id="8362b-106">此步骤需要刚刚上载或涉及上载，然后选择下载的完全同步。</span><span class="sxs-lookup"><span data-stu-id="8362b-106">This involves just uploading, or a full synchronization involving an upload and then a download.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8362b-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="8362b-107">Quick info</span></span>

```cpp
struct SYNCCONT 
{ 
   ULONG   ulFlags; 
   UINT   iEnt; 
   UINT   cEnt; 
   LPVOID    pvReserved; 
   LPSPropTagArray   ptagaReserved; 
   LPSSortOrderSet   psosReserved; 
};
```

## <a name="members"></a><span data-ttu-id="8362b-108">Members</span><span class="sxs-lookup"><span data-stu-id="8362b-108">Members</span></span>

<span data-ttu-id="8362b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8362b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="8362b-110">[in]同步过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="8362b-110">[in] Flags to determine the appropriate behavior during synchronization.</span></span>
    
  - <span data-ttu-id="8362b-111">UPC_OK</span><span class="sxs-lookup"><span data-stu-id="8362b-111">UPC_OK</span></span>
    
  - <span data-ttu-id="8362b-112">[in]上载或完全同步成功。</span><span class="sxs-lookup"><span data-stu-id="8362b-112">[in] Upload or full synchronization was successful.</span></span> <span data-ttu-id="8362b-113">客户端与服务器同步信息后设置此。</span><span class="sxs-lookup"><span data-stu-id="8362b-113">The client sets this after synchronizing information with the server.</span></span>
    
<span data-ttu-id="8362b-114">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="8362b-114">_iEnt_</span></span>
  
> <span data-ttu-id="8362b-115">[输出]要跟踪同步中的 _%_ 由指定的文件夹的数量的内容索引。</span><span class="sxs-lookup"><span data-stu-id="8362b-115">[out] Index to track synchronizing the contents in the number of folders specified by  _cEnt_.</span></span>
    
<span data-ttu-id="8362b-116">_%_</span><span class="sxs-lookup"><span data-stu-id="8362b-116">_cEnt_</span></span>
  
> <span data-ttu-id="8362b-117">[输出]要复制的文件夹的数量。</span><span class="sxs-lookup"><span data-stu-id="8362b-117">[out] Number of folders to be replicated.</span></span>
    
<span data-ttu-id="8362b-118">_pvReserved_</span><span class="sxs-lookup"><span data-stu-id="8362b-118">_pvReserved_</span></span>
  
> <span data-ttu-id="8362b-119">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8362b-119">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="8362b-120">_ptagaReserved_</span><span class="sxs-lookup"><span data-stu-id="8362b-120">_ptagaReserved_</span></span>
  
> <span data-ttu-id="8362b-121">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8362b-121">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="8362b-122">_psosReserved_</span><span class="sxs-lookup"><span data-stu-id="8362b-122">_psosReserved_</span></span>
  
> <span data-ttu-id="8362b-123">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="8362b-123">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8362b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8362b-124">See also</span></span>

- [<span data-ttu-id="8362b-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="8362b-125">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="8362b-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="8362b-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="8362b-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="8362b-127">MAPI Constants</span></span>](mapi-constants.md)

