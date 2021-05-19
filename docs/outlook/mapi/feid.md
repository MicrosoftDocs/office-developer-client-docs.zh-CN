---
title: FEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dde7eec-df3d-723c-db08-7ff0b6107a0b
description: 上次修改时间：2012 年 7 月 2 日
ms.openlocfilehash: 88716719857cfd623d30a3684fc997ea8019455e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409809"
---
# <a name="feid"></a><span data-ttu-id="ce02e-103">FEID</span><span class="sxs-lookup"><span data-stu-id="ce02e-103">FEID</span></span>

 
  
<span data-ttu-id="ce02e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce02e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce02e-105">文件夹的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce02e-105">Identifier for a folder.</span></span> <span data-ttu-id="ce02e-106">它包含条目标识符和其他相关信息。</span><span class="sxs-lookup"><span data-stu-id="ce02e-106">It contains an entry identifier and other relevant information.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ce02e-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="ce02e-107">Quick info</span></span>

```cpp
struct FEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltid; 
};
```

## <a name="members"></a><span data-ttu-id="ce02e-108">成员</span><span class="sxs-lookup"><span data-stu-id="ce02e-108">Members</span></span>

 <span data-ttu-id="ce02e-109">_abFlags_</span><span class="sxs-lookup"><span data-stu-id="ce02e-109">_abFlags_</span></span>
  
> <span data-ttu-id="ce02e-110">文件夹的 4 字节条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ce02e-110">4-byte entry identifier for the folder.</span></span> <span data-ttu-id="ce02e-111">有关 MAPI 条目标识符详细信息，请参阅 **[ENTRYID](entryid.md)**。</span><span class="sxs-lookup"><span data-stu-id="ce02e-111">For more information about MAPI entry identifiers, see **[ENTRYID](entryid.md)**.</span></span> 
    
 <span data-ttu-id="ce02e-112">_muid_</span><span class="sxs-lookup"><span data-stu-id="ce02e-112">_muid_</span></span>
  
> <span data-ttu-id="ce02e-113">标识存储提供程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ce02e-113">GUID that identifies the store provider.</span></span> <span data-ttu-id="ce02e-114">有关 **MAPIUID** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="ce02e-114">See mapidefs.h for the type definition of **MAPIUID**.</span></span> 
    
 <span data-ttu-id="ce02e-115">_占位符_</span><span class="sxs-lookup"><span data-stu-id="ce02e-115">_placeholder_</span></span>
  
> <span data-ttu-id="ce02e-116">此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="ce02e-116">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="ce02e-117">_ltid_</span><span class="sxs-lookup"><span data-stu-id="ce02e-117">_ltid_</span></span>
  
> <span data-ttu-id="ce02e-118">文件夹的长期 ID。</span><span class="sxs-lookup"><span data-stu-id="ce02e-118">Long-term ID of the folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ce02e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce02e-119">See also</span></span>



[<span data-ttu-id="ce02e-120">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="ce02e-120">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="ce02e-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ce02e-121">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="ce02e-122">LTID</span><span class="sxs-lookup"><span data-stu-id="ce02e-122">LTID</span></span>](ltid.md)
  
[<span data-ttu-id="ce02e-123">UPFLD</span><span class="sxs-lookup"><span data-stu-id="ce02e-123">UPFLD</span></span>](upfld.md)
  
[<span data-ttu-id="ce02e-124">SYNC</span><span class="sxs-lookup"><span data-stu-id="ce02e-124">SYNC</span></span>](sync.md)

