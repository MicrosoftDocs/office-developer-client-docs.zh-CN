---
title: MEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa8f18d9-691d-d0cc-a660-f15ea6cff6ce
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: a9aea0db700de9c82aa2a41a443ebf03da8ce9b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430306"
---
# <a name="meid"></a><span data-ttu-id="c16d8-103">MEID</span><span class="sxs-lookup"><span data-stu-id="c16d8-103">MEID</span></span>

 
  
<span data-ttu-id="c16d8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c16d8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c16d8-105">项目标识符Outlook项。</span><span class="sxs-lookup"><span data-stu-id="c16d8-105">Identifier for an Outlook item.</span></span> <span data-ttu-id="c16d8-106">它包含条目标识符和其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="c16d8-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="c16d8-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="c16d8-107">Quick info</span></span>

```cpp
struct MEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltidFld; 
    LTID ltidMsg; 
};
```

## <a name="members"></a><span data-ttu-id="c16d8-108">成员</span><span class="sxs-lookup"><span data-stu-id="c16d8-108">Members</span></span>

 <span data-ttu-id="c16d8-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="c16d8-109">_abFlags_</span></span>
  
> <span data-ttu-id="c16d8-110">项目项的 4 字节Outlook标识符。</span><span class="sxs-lookup"><span data-stu-id="c16d8-110">4-byte entry identifier for the Outlook item.</span></span> <span data-ttu-id="c16d8-111">有关 MAPI 条目标识符详细信息，请参阅 **[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="c16d8-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="c16d8-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="c16d8-112">_muid_</span></span>
  
> <span data-ttu-id="c16d8-113">标识存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c16d8-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="c16d8-114">有关 **MAPIUID** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="c16d8-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="c16d8-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="c16d8-115">_placeholder_</span></span>
  
> <span data-ttu-id="c16d8-116">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="c16d8-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="c16d8-117">_ltidFld_</span><span class="sxs-lookup"><span data-stu-id="c16d8-117">_ltidFld_</span></span>
  
> <span data-ttu-id="c16d8-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="c16d8-118">Long-term ID of the folder.</span></span>
    
 <span data-ttu-id="c16d8-119">_ltidMsg_</span><span class="sxs-lookup"><span data-stu-id="c16d8-119">_ltidMsg_</span></span>
  
> <span data-ttu-id="c16d8-120">项目的长期 ID Outlook ID。</span><span class="sxs-lookup"><span data-stu-id="c16d8-120">Long-term ID of the Outlook item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c16d8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c16d8-121">See also</span></span>



[<span data-ttu-id="c16d8-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="c16d8-122">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="c16d8-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="c16d8-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="c16d8-124">LTID</span><span class="sxs-lookup"><span data-stu-id="c16d8-124">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="c16d8-125">SYNC</span><span class="sxs-lookup"><span data-stu-id="c16d8-125">SYNC</span></span>](sync.md)
  
[<span data-ttu-id="c16d8-126">UPMSG</span><span class="sxs-lookup"><span data-stu-id="c16d8-126">UPMSG</span></span>](upmsg.md)

