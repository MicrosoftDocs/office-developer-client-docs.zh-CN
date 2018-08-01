---
title: HDRSYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bf6892d0-a923-e926-5361-59efa49ebdc0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bd1c327eb2042957c8fb043736950af3dae520b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775073"
---
# <a name="hdrsync"></a><span data-ttu-id="2e41d-103">HDRSYNC</span><span class="sxs-lookup"><span data-stu-id="2e41d-103">HDRSYNC</span></span>

  
  
<span data-ttu-id="2e41d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2e41d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2e41d-105">同步过程中[下载邮件头状态](download-message-header-state.md)的邮件头信息。</span><span class="sxs-lookup"><span data-stu-id="2e41d-105">Information for synchronizing a message header during the [download message header state](download-message-header-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2e41d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="2e41d-106">Quick info</span></span>

```cpp
struct HDRSYNC 
{ 
    UPMSG *pupmsg; 
    FEID feidPar; 
    LPSTREAM pstmReserved; 
    ULONG ulFlags; 
    LPMESSAGE pmsgFull; 
};
```

## <a name="members"></a><span data-ttu-id="2e41d-107">Members</span><span class="sxs-lookup"><span data-stu-id="2e41d-107">Members</span></span>

 <span data-ttu-id="2e41d-108">_pupmsg_</span><span class="sxs-lookup"><span data-stu-id="2e41d-108">_pupmsg_</span></span>
  
- <span data-ttu-id="2e41d-109">[输出]本地存储中的当前邮件头信息。</span><span class="sxs-lookup"><span data-stu-id="2e41d-109">[out] Information for the current message header in the local store.</span></span>
    
 <span data-ttu-id="2e41d-110">_feidPar_</span><span class="sxs-lookup"><span data-stu-id="2e41d-110">_feidPar_</span></span>
  
- <span data-ttu-id="2e41d-111">[输出]邮件项目的父文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="2e41d-111">[out] Entry ID for the parent folder of the message item.</span></span>
    
 <span data-ttu-id="2e41d-112">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="2e41d-112">_pstmReserved_</span></span>
  
- <span data-ttu-id="2e41d-113">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="2e41d-113">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="2e41d-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2e41d-114">_ulFlags_</span></span>
  
- <span data-ttu-id="2e41d-115">[in]若要修改行为的标志：</span><span class="sxs-lookup"><span data-stu-id="2e41d-115">[in] Flags to modify behavior:</span></span>
    
- <span data-ttu-id="2e41d-116">HSF_LOCAL</span><span class="sxs-lookup"><span data-stu-id="2e41d-116">HSF_LOCAL</span></span>
    
  - <span data-ttu-id="2e41d-117">[in]整个项目位于相同的本地存储用作的标头项。</span><span class="sxs-lookup"><span data-stu-id="2e41d-117">[in] Full item resides in the same local store as the header item.</span></span>
    
- <span data-ttu-id="2e41d-118">HSF_COPYDESTRUCTIVE</span><span class="sxs-lookup"><span data-stu-id="2e41d-118">HSF_COPYDESTRUCTIVE</span></span>
    
  -  <span data-ttu-id="2e41d-119">[in]优化内部复制操作。</span><span class="sxs-lookup"><span data-stu-id="2e41d-119">[in] Optimize internal copy operations.</span></span> <span data-ttu-id="2e41d-120">这可能会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="2e41d-120">This might cause data loss.</span></span> <span data-ttu-id="2e41d-121">必须设置**HSF_LOCAL** 。</span><span class="sxs-lookup"><span data-stu-id="2e41d-121">**HSF_LOCAL** must be set.</span></span> 
    
- <span data-ttu-id="2e41d-122">HSF_OK</span><span class="sxs-lookup"><span data-stu-id="2e41d-122">HSF_OK</span></span>
    
  - <span data-ttu-id="2e41d-123">[in]标头同步成功。</span><span class="sxs-lookup"><span data-stu-id="2e41d-123">[in] Header synchronization was successful.</span></span> <span data-ttu-id="2e41d-124">客户端设置从服务器下载信息之后。</span><span class="sxs-lookup"><span data-stu-id="2e41d-124">The client sets this after downloading information from the server.</span></span>
    
     <span data-ttu-id="2e41d-125">_pmsgFull_</span><span class="sxs-lookup"><span data-stu-id="2e41d-125">_pmsgFull_</span></span>
    
  - <span data-ttu-id="2e41d-126">[in]从服务器下载包括邮件头的完整的邮件项目。</span><span class="sxs-lookup"><span data-stu-id="2e41d-126">[in] The full message item including the message header downloaded from the server.</span></span> <span data-ttu-id="2e41d-127">请参阅 mapidefs.h **LPMESSAGE**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e41d-127">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2e41d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e41d-128">See also</span></span>



[<span data-ttu-id="2e41d-129">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="2e41d-129">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="2e41d-130">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="2e41d-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="2e41d-131">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2e41d-131">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="2e41d-132">FEID</span><span class="sxs-lookup"><span data-stu-id="2e41d-132">FEID</span></span>](feid.md)

