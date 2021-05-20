---
title: SYNCCONT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7b4307a3-5a8c-89bf-1113-2549556a7fe7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afba7fa718a35d33966d45289461313e349ef2e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430404"
---
# <a name="synccont"></a><span data-ttu-id="94e62-103">SYNCCONT</span><span class="sxs-lookup"><span data-stu-id="94e62-103">SYNCCONT</span></span>

<span data-ttu-id="94e62-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94e62-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94e62-105">有关在同步内容状态期间将本地存储中指定文件夹的内容与服务器 [同步的信息](synchronize-contents-state.md)。</span><span class="sxs-lookup"><span data-stu-id="94e62-105">Information for synchronizing the contents of specified folders in a local store with the server during the [synchronize contents state](synchronize-contents-state.md).</span></span> <span data-ttu-id="94e62-106">这仅涉及上载，或涉及上载和下载的完全同步。</span><span class="sxs-lookup"><span data-stu-id="94e62-106">This involves just uploading, or a full synchronization involving an upload and then a download.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="94e62-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="94e62-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="94e62-108">成员</span><span class="sxs-lookup"><span data-stu-id="94e62-108">Members</span></span>

<span data-ttu-id="94e62-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="94e62-109">_ulFlags_</span></span>
  
> <span data-ttu-id="94e62-110">[in]用于确定同步期间的适当行为的标志。</span><span class="sxs-lookup"><span data-stu-id="94e62-110">[in] Flags to determine the appropriate behavior during synchronization.</span></span>
    
  - <span data-ttu-id="94e62-111">UPC_OK</span><span class="sxs-lookup"><span data-stu-id="94e62-111">UPC_OK</span></span>
    
  - <span data-ttu-id="94e62-112">[in]Upload同步或完全同步成功。</span><span class="sxs-lookup"><span data-stu-id="94e62-112">[in] Upload or full synchronization was successful.</span></span> <span data-ttu-id="94e62-113">客户端在将信息与服务器同步后进行设置。</span><span class="sxs-lookup"><span data-stu-id="94e62-113">The client sets this after synchronizing information with the server.</span></span>
    
<span data-ttu-id="94e62-114">_iEnt_</span><span class="sxs-lookup"><span data-stu-id="94e62-114">_iEnt_</span></span>
  
> <span data-ttu-id="94e62-115">[out]索引，跟踪同步 cEnt 指定的文件夹数量  _中的内容_。</span><span class="sxs-lookup"><span data-stu-id="94e62-115">[out] Index to track synchronizing the contents in the number of folders specified by  _cEnt_.</span></span>
    
<span data-ttu-id="94e62-116">_cEnt_</span><span class="sxs-lookup"><span data-stu-id="94e62-116">_cEnt_</span></span>
  
> <span data-ttu-id="94e62-117">[out]要复制的文件夹数。</span><span class="sxs-lookup"><span data-stu-id="94e62-117">[out] Number of folders to be replicated.</span></span>
    
<span data-ttu-id="94e62-118">_pvReserved_</span><span class="sxs-lookup"><span data-stu-id="94e62-118">_pvReserved_</span></span>
  
> <span data-ttu-id="94e62-119">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="94e62-119">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="94e62-120">_ptagaReserved_</span><span class="sxs-lookup"><span data-stu-id="94e62-120">_ptagaReserved_</span></span>
  
> <span data-ttu-id="94e62-121">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="94e62-121">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="94e62-122">_psosReserved_</span><span class="sxs-lookup"><span data-stu-id="94e62-122">_psosReserved_</span></span>
  
> <span data-ttu-id="94e62-123">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="94e62-123">This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="94e62-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94e62-124">See also</span></span>

- [<span data-ttu-id="94e62-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="94e62-125">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="94e62-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="94e62-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="94e62-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="94e62-127">MAPI Constants</span></span>](mapi-constants.md)

