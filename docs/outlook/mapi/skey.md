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
ms.openlocfilehash: 26b08535d81cb961ed0ace70ea227316b30cd526
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573458"
---
# <a name="skey"></a><span data-ttu-id="4d083-103">SKEY</span><span class="sxs-lookup"><span data-stu-id="4d083-103">SKEY</span></span>

  
  
<span data-ttu-id="4d083-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d083-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d083-105">某个 Outlook 项目的的源键。</span><span class="sxs-lookup"><span data-stu-id="4d083-105">Source key for an Outlook item.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4d083-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="4d083-106">Quick info</span></span>

```cpp
struct SKEY 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
};
```

## <a name="members"></a><span data-ttu-id="4d083-107">Members</span><span class="sxs-lookup"><span data-stu-id="4d083-107">Members</span></span>

 <span data-ttu-id="4d083-108">_guid_</span><span class="sxs-lookup"><span data-stu-id="4d083-108">_guid_</span></span>
  
> <span data-ttu-id="4d083-109">创建对象的服务器的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4d083-109">GUID of the server creating the object.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4d083-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d083-110">See also</span></span>



[<span data-ttu-id="4d083-111">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="4d083-111">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="4d083-112">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="4d083-112">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="4d083-113">UPDELE</span><span class="sxs-lookup"><span data-stu-id="4d083-113">UPDELE</span></span>](updele.md)
  
[<span data-ttu-id="4d083-114">UPMSG</span><span class="sxs-lookup"><span data-stu-id="4d083-114">UPMSG</span></span>](upmsg.md)
  
[<span data-ttu-id="4d083-115">UPREADE</span><span class="sxs-lookup"><span data-stu-id="4d083-115">UPREADE</span></span>](upreade.md)

