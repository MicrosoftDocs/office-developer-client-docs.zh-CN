---
title: MEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa8f18d9-691d-d0cc-a660-f15ea6cff6ce
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 1b725dc5151f1f088f2547a1ef82d322c8458b6e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776527"
---
# <a name="meid"></a><span data-ttu-id="ae97c-103">MEID</span><span class="sxs-lookup"><span data-stu-id="ae97c-103">MEID</span></span>

 
  
<span data-ttu-id="ae97c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ae97c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ae97c-105">某个 Outlook 项目的的标识符。</span><span class="sxs-lookup"><span data-stu-id="ae97c-105">Identifier for an Outlook item.</span></span> <span data-ttu-id="ae97c-106">它包含的项标识符以及其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="ae97c-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ae97c-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="ae97c-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="ae97c-108">Members</span><span class="sxs-lookup"><span data-stu-id="ae97c-108">Members</span></span>

 <span data-ttu-id="ae97c-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="ae97c-109">_abFlags_</span></span>
  
> <span data-ttu-id="ae97c-110">对 Outlook 项目的 4 字节条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ae97c-110">4-byte entry identifier for the Outlook item.</span></span> <span data-ttu-id="ae97c-111">有关 MAPI 项标识符的详细信息，请参阅**[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="ae97c-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="ae97c-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="ae97c-112">_muid_</span></span>
  
> <span data-ttu-id="ae97c-113">标识的存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ae97c-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="ae97c-114">请参阅 mapidefs.h **MAPIUID**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="ae97c-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="ae97c-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="ae97c-115">_placeholder_</span></span>
  
> <span data-ttu-id="ae97c-116">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="ae97c-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="ae97c-117">_ltidFld_</span><span class="sxs-lookup"><span data-stu-id="ae97c-117">_ltidFld_</span></span>
  
> <span data-ttu-id="ae97c-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="ae97c-118">Long-term ID of the folder.</span></span>
    
 <span data-ttu-id="ae97c-119">_ltidMsg_</span><span class="sxs-lookup"><span data-stu-id="ae97c-119">_ltidMsg_</span></span>
  
> <span data-ttu-id="ae97c-120">Outlook 项目的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="ae97c-120">Long-term ID of the Outlook item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae97c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae97c-121">See also</span></span>



[<span data-ttu-id="ae97c-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="ae97c-122">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="ae97c-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="ae97c-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="ae97c-124">LTID</span><span class="sxs-lookup"><span data-stu-id="ae97c-124">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="ae97c-125">SYNC</span><span class="sxs-lookup"><span data-stu-id="ae97c-125">SYNC</span></span>](sync.md)
  
[<span data-ttu-id="ae97c-126">UPMSG</span><span class="sxs-lookup"><span data-stu-id="ae97c-126">UPMSG</span></span>](upmsg.md)

