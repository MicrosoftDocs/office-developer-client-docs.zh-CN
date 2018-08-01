---
title: SKEY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f1e8291-6153-c308-94be-ca6745ea86a4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f4ece0662b72047b785b03f3134c96fac48c219a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778813"
---
# <a name="skey"></a><span data-ttu-id="5f650-103">SKEY</span><span class="sxs-lookup"><span data-stu-id="5f650-103">SKEY</span></span>

  
  
<span data-ttu-id="5f650-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5f650-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5f650-105">某个 Outlook 项目的的源键。</span><span class="sxs-lookup"><span data-stu-id="5f650-105">Source key for an Outlook item.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5f650-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="5f650-106">Quick info</span></span>

```cpp
struct SKEY 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
};
```

## <a name="members"></a><span data-ttu-id="5f650-107">Members</span><span class="sxs-lookup"><span data-stu-id="5f650-107">Members</span></span>

 <span data-ttu-id="5f650-108">_guid_</span><span class="sxs-lookup"><span data-stu-id="5f650-108">_guid_</span></span>
  
> <span data-ttu-id="5f650-109">创建对象的服务器的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5f650-109">GUID of the server creating the object.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f650-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f650-110">See also</span></span>



[<span data-ttu-id="5f650-111">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="5f650-111">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="5f650-112">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="5f650-112">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="5f650-113">UPDELE</span><span class="sxs-lookup"><span data-stu-id="5f650-113">UPDELE</span></span>](updele.md)
  
[<span data-ttu-id="5f650-114">UPMSG</span><span class="sxs-lookup"><span data-stu-id="5f650-114">UPMSG</span></span>](upmsg.md)
  
[<span data-ttu-id="5f650-115">UPREADE</span><span class="sxs-lookup"><span data-stu-id="5f650-115">UPREADE</span></span>](upreade.md)

