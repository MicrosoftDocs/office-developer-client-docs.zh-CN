---
title: FEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dde7eec-df3d-723c-db08-7ff0b6107a0b
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 3e534f91863e2a1300e03d112d1f532f486eedd9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588305"
---
# <a name="feid"></a><span data-ttu-id="e7927-103">FEID</span><span class="sxs-lookup"><span data-stu-id="e7927-103">FEID</span></span>

 
  
<span data-ttu-id="e7927-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7927-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e7927-105">文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="e7927-105">Identifier for a folder.</span></span> <span data-ttu-id="e7927-106">它包含的项标识符以及其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="e7927-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e7927-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="e7927-107">Quick info</span></span>

```cpp
struct FEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltid; 
};
```

## <a name="members"></a><span data-ttu-id="e7927-108">Members</span><span class="sxs-lookup"><span data-stu-id="e7927-108">Members</span></span>

 <span data-ttu-id="e7927-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="e7927-109">_abFlags_</span></span>
  
> <span data-ttu-id="e7927-110">4 字节条目的文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="e7927-110">4-byte entry identifier for the folder.</span></span> <span data-ttu-id="e7927-111">有关 MAPI 项标识符的详细信息，请参阅**[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="e7927-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="e7927-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="e7927-112">_muid_</span></span>
  
> <span data-ttu-id="e7927-113">标识的存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e7927-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="e7927-114">请参阅 mapidefs.h **MAPIUID**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="e7927-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="e7927-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="e7927-115">_placeholder_</span></span>
  
> <span data-ttu-id="e7927-116">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="e7927-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="e7927-117">_ltid_</span><span class="sxs-lookup"><span data-stu-id="e7927-117">_ltid_</span></span>
  
> <span data-ttu-id="e7927-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="e7927-118">Long-term ID of the folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e7927-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7927-119">See also</span></span>



[<span data-ttu-id="e7927-120">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="e7927-120">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e7927-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e7927-121">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="e7927-122">LTID</span><span class="sxs-lookup"><span data-stu-id="e7927-122">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="e7927-123">UPFLD</span><span class="sxs-lookup"><span data-stu-id="e7927-123">UPFLD</span></span>](upfld.md)
  
[<span data-ttu-id="e7927-124">SYNC</span><span class="sxs-lookup"><span data-stu-id="e7927-124">SYNC</span></span>](sync.md)

