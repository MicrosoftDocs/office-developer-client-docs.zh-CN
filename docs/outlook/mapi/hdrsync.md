---
title: HDRSYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bf6892d0-a923-e926-5361-59efa49ebdc0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2131197ca24804eec74270100fa70c05c47a27cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410250"
---
# <a name="hdrsync"></a><span data-ttu-id="29f78-103">HDRSYNC</span><span class="sxs-lookup"><span data-stu-id="29f78-103">HDRSYNC</span></span>

  
  
<span data-ttu-id="29f78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29f78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29f78-105">有关在[下载邮件头状态](download-message-header-state.md)期间同步邮件头的信息。</span><span class="sxs-lookup"><span data-stu-id="29f78-105">Information for synchronizing a message header during the [download message header state](download-message-header-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="29f78-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="29f78-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="29f78-107">成员</span><span class="sxs-lookup"><span data-stu-id="29f78-107">Members</span></span>

 <span data-ttu-id="29f78-108">_pupmsg_</span><span class="sxs-lookup"><span data-stu-id="29f78-108">_pupmsg_</span></span>
  
- <span data-ttu-id="29f78-109">排除本地存储中当前邮件头的信息。</span><span class="sxs-lookup"><span data-stu-id="29f78-109">[out] Information for the current message header in the local store.</span></span>
    
 <span data-ttu-id="29f78-110">_feidPar_</span><span class="sxs-lookup"><span data-stu-id="29f78-110">_feidPar_</span></span>
  
- <span data-ttu-id="29f78-111">排除邮件项目的父文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="29f78-111">[out] Entry ID for the parent folder of the message item.</span></span>
    
 <span data-ttu-id="29f78-112">_pstmReserved_</span><span class="sxs-lookup"><span data-stu-id="29f78-112">_pstmReserved_</span></span>
  
- <span data-ttu-id="29f78-113">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="29f78-113">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
 <span data-ttu-id="29f78-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="29f78-114">_ulFlags_</span></span>
  
- <span data-ttu-id="29f78-115">实时修改行为的标志:</span><span class="sxs-lookup"><span data-stu-id="29f78-115">[in] Flags to modify behavior:</span></span>
    
- <span data-ttu-id="29f78-116">HSF_LOCAL</span><span class="sxs-lookup"><span data-stu-id="29f78-116">HSF_LOCAL</span></span>
    
  - <span data-ttu-id="29f78-117">实时完整项目位于与标题项目相同的本地存储中。</span><span class="sxs-lookup"><span data-stu-id="29f78-117">[in] Full item resides in the same local store as the header item.</span></span>
    
- <span data-ttu-id="29f78-118">HSF_COPYDESTRUCTIVE</span><span class="sxs-lookup"><span data-stu-id="29f78-118">HSF_COPYDESTRUCTIVE</span></span>
    
  -  <span data-ttu-id="29f78-119">实时优化内部副本操作。</span><span class="sxs-lookup"><span data-stu-id="29f78-119">[in] Optimize internal copy operations.</span></span> <span data-ttu-id="29f78-120">这可能会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="29f78-120">This might cause data loss.</span></span> <span data-ttu-id="29f78-121">必须设置**HSF_LOCAL** 。</span><span class="sxs-lookup"><span data-stu-id="29f78-121">**HSF_LOCAL** must be set.</span></span> 
    
- <span data-ttu-id="29f78-122">HSF_OK</span><span class="sxs-lookup"><span data-stu-id="29f78-122">HSF_OK</span></span>
    
  - <span data-ttu-id="29f78-123">实时标头同步成功。</span><span class="sxs-lookup"><span data-stu-id="29f78-123">[in] Header synchronization was successful.</span></span> <span data-ttu-id="29f78-124">客户端从服务器下载信息之后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="29f78-124">The client sets this after downloading information from the server.</span></span>
    
     <span data-ttu-id="29f78-125">_pmsgFull_</span><span class="sxs-lookup"><span data-stu-id="29f78-125">_pmsgFull_</span></span>
    
  - <span data-ttu-id="29f78-126">实时包含从服务器下载的邮件头的完整邮件项目。</span><span class="sxs-lookup"><span data-stu-id="29f78-126">[in] The full message item including the message header downloaded from the server.</span></span> <span data-ttu-id="29f78-127">有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="29f78-127">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="29f78-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29f78-128">See also</span></span>



[<span data-ttu-id="29f78-129">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="29f78-129">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="29f78-130">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="29f78-130">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="29f78-131">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="29f78-131">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="29f78-132">FEID</span><span class="sxs-lookup"><span data-stu-id="29f78-132">FEID</span></span>](feid.md)

