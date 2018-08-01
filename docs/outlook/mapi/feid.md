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
ms.openlocfilehash: bb2d347d218a7c33a2184bf1fcf181a11fa7d8fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774923"
---
# <a name="feid"></a><span data-ttu-id="fa602-103">FEID</span><span class="sxs-lookup"><span data-stu-id="fa602-103">FEID</span></span>

 
  
<span data-ttu-id="fa602-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fa602-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fa602-105">文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="fa602-105">Identifier for a folder.</span></span> <span data-ttu-id="fa602-106">它包含的项标识符以及其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="fa602-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fa602-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="fa602-107">Quick info</span></span>

```cpp
struct FEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltid; 
};
```

## <a name="members"></a><span data-ttu-id="fa602-108">Members</span><span class="sxs-lookup"><span data-stu-id="fa602-108">Members</span></span>

 <span data-ttu-id="fa602-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="fa602-109">_abFlags_</span></span>
  
> <span data-ttu-id="fa602-110">4 字节条目的文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="fa602-110">4-byte entry identifier for the folder.</span></span> <span data-ttu-id="fa602-111">有关 MAPI 项标识符的详细信息，请参阅**[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="fa602-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="fa602-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="fa602-112">_muid_</span></span>
  
> <span data-ttu-id="fa602-113">标识的存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="fa602-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="fa602-114">请参阅 mapidefs.h **MAPIUID**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="fa602-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="fa602-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="fa602-115">_placeholder_</span></span>
  
> <span data-ttu-id="fa602-116">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="fa602-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="fa602-117">_ltid_</span><span class="sxs-lookup"><span data-stu-id="fa602-117">_ltid_</span></span>
  
> <span data-ttu-id="fa602-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="fa602-118">Long-term ID of the folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fa602-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa602-119">See also</span></span>



[<span data-ttu-id="fa602-120">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="fa602-120">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="fa602-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="fa602-121">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="fa602-122">LTID</span><span class="sxs-lookup"><span data-stu-id="fa602-122">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="fa602-123">UPFLD</span><span class="sxs-lookup"><span data-stu-id="fa602-123">UPFLD</span></span>](upfld.md)
  
[<span data-ttu-id="fa602-124">SYNC</span><span class="sxs-lookup"><span data-stu-id="fa602-124">SYNC</span></span>](sync.md)

