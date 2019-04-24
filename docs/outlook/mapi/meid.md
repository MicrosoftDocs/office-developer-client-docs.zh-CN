---
title: MEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa8f18d9-691d-d0cc-a660-f15ea6cff6ce
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: a9aea0db700de9c82aa2a41a443ebf03da8ce9b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356971"
---
# <a name="meid"></a><span data-ttu-id="2265e-103">MEID</span><span class="sxs-lookup"><span data-stu-id="2265e-103">MEID</span></span>

 
  
<span data-ttu-id="2265e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2265e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2265e-105">Outlook 项目的标识符。</span><span class="sxs-lookup"><span data-stu-id="2265e-105">Identifier for an Outlook item.</span></span> <span data-ttu-id="2265e-106">它包含条目标识符和其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="2265e-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2265e-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="2265e-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="2265e-108">成员</span><span class="sxs-lookup"><span data-stu-id="2265e-108">Members</span></span>

 <span data-ttu-id="2265e-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="2265e-109">_abFlags_</span></span>
  
> <span data-ttu-id="2265e-110">4字节的 Outlook 项目标识符。</span><span class="sxs-lookup"><span data-stu-id="2265e-110">4-byte entry identifier for the Outlook item.</span></span> <span data-ttu-id="2265e-111">有关 MAPI 条目标识符的详细信息, 请参阅**[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="2265e-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="2265e-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="2265e-112">_muid_</span></span>
  
> <span data-ttu-id="2265e-113">标识存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="2265e-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="2265e-114">有关**MAPIUID**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="2265e-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="2265e-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="2265e-115">_placeholder_</span></span>
  
> <span data-ttu-id="2265e-116">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="2265e-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="2265e-117">_ltidFld_</span><span class="sxs-lookup"><span data-stu-id="2265e-117">_ltidFld_</span></span>
  
> <span data-ttu-id="2265e-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="2265e-118">Long-term ID of the folder.</span></span>
    
 <span data-ttu-id="2265e-119">_ltidMsg_</span><span class="sxs-lookup"><span data-stu-id="2265e-119">_ltidMsg_</span></span>
  
> <span data-ttu-id="2265e-120">Outlook 项目的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="2265e-120">Long-term ID of the Outlook item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2265e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2265e-121">See also</span></span>



[<span data-ttu-id="2265e-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="2265e-122">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="2265e-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="2265e-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="2265e-124">LTID</span><span class="sxs-lookup"><span data-stu-id="2265e-124">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="2265e-125">同步</span><span class="sxs-lookup"><span data-stu-id="2265e-125">SYNC</span></span>](sync.md)
  
[<span data-ttu-id="2265e-126">UPMSG</span><span class="sxs-lookup"><span data-stu-id="2265e-126">UPMSG</span></span>](upmsg.md)

