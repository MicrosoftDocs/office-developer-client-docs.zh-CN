---
title: SKEY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f1e8291-6153-c308-94be-ca6745ea86a4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c417e6f4412bc40e8c2ebc056514eb96f60798f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282675"
---
# <a name="skey"></a><span data-ttu-id="a9c40-103">SKEY</span><span class="sxs-lookup"><span data-stu-id="a9c40-103">SKEY</span></span>

  
  
<span data-ttu-id="a9c40-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9c40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9c40-105">Outlook 项目的源键。</span><span class="sxs-lookup"><span data-stu-id="a9c40-105">Source key for an Outlook item.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a9c40-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="a9c40-106">Quick info</span></span>

```cpp
struct SKEY 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
};
```

## <a name="members"></a><span data-ttu-id="a9c40-107">成员</span><span class="sxs-lookup"><span data-stu-id="a9c40-107">Members</span></span>

 <span data-ttu-id="a9c40-108">_guid_</span><span class="sxs-lookup"><span data-stu-id="a9c40-108">_guid_</span></span>
  
> <span data-ttu-id="a9c40-109">创建对象的服务器的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a9c40-109">GUID of the server creating the object.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a9c40-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9c40-110">See also</span></span>



[<span data-ttu-id="a9c40-111">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="a9c40-111">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="a9c40-112">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="a9c40-112">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="a9c40-113">UPDELE</span><span class="sxs-lookup"><span data-stu-id="a9c40-113">UPDELE</span></span>](updele.md)
  
[<span data-ttu-id="a9c40-114">UPMSG</span><span class="sxs-lookup"><span data-stu-id="a9c40-114">UPMSG</span></span>](upmsg.md)
  
[<span data-ttu-id="a9c40-115">UPREADE</span><span class="sxs-lookup"><span data-stu-id="a9c40-115">UPREADE</span></span>](upreade.md)

