---
title: LTID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a412ba-3f74-ba94-0ffa-01dae63fc157
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ea877c9328279322de0f15e5755096e74819425
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357412"
---
# <a name="ltid"></a><span data-ttu-id="b3725-103">LTID</span><span class="sxs-lookup"><span data-stu-id="b3725-103">LTID</span></span>

  
  
<span data-ttu-id="b3725-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3725-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3725-105">Outlook 应用商店中的对象的常规长期术语 ID。</span><span class="sxs-lookup"><span data-stu-id="b3725-105">Generic Long Term ID of an object in an Outlook store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b3725-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b3725-106">Quick info</span></span>

```cpp
struct LTID 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
    WORD wLevel; 
};
```

## <a name="members"></a><span data-ttu-id="b3725-107">成员</span><span class="sxs-lookup"><span data-stu-id="b3725-107">Members</span></span>

 <span data-ttu-id="b3725-108">_guid_</span><span class="sxs-lookup"><span data-stu-id="b3725-108">_guid_</span></span>
  
- <span data-ttu-id="b3725-109">排除创建该对象的服务器的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b3725-109">[out] The GUID of the server that created the object.</span></span>
    
 <span data-ttu-id="b3725-110">_globcnt_</span><span class="sxs-lookup"><span data-stu-id="b3725-110">_globcnt_</span></span>
  
- <span data-ttu-id="b3725-111">排除一个6字节的唯一编号, 用于标识 Outlook 存储中的对象。</span><span class="sxs-lookup"><span data-stu-id="b3725-111">[out] A 6-byte unique number that identifies the object within the Outlook store.</span></span>
    
 <span data-ttu-id="b3725-112">_wLevel_</span><span class="sxs-lookup"><span data-stu-id="b3725-112">_wLevel_</span></span>
  
- <span data-ttu-id="b3725-113">排除Exchange 收藏的公用文件夹的条目 ID 的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="b3725-113">[out] The hierarchy level of the entry ID for an Exchange Favorite Public folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3725-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3725-114">See also</span></span>



[<span data-ttu-id="b3725-115">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="b3725-115">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="b3725-116">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="b3725-116">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="b3725-117">FEID</span><span class="sxs-lookup"><span data-stu-id="b3725-117">FEID</span></span>](feid.md)

