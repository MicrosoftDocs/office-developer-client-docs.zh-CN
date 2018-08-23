---
title: LTID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a412ba-3f74-ba94-0ffa-01dae63fc157
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29dd2e3b47d0f43df7824274d2fdcc4f7f16eeb3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569853"
---
# <a name="ltid"></a><span data-ttu-id="7b135-103">LTID</span><span class="sxs-lookup"><span data-stu-id="7b135-103">LTID</span></span>

  
  
<span data-ttu-id="7b135-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b135-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b135-105">Outlook 存储区中某个对象的通用长术语 ID。</span><span class="sxs-lookup"><span data-stu-id="7b135-105">Generic Long Term ID of an object in an Outlook store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7b135-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7b135-106">Quick info</span></span>

```cpp
struct LTID 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
    WORD wLevel; 
};
```

## <a name="members"></a><span data-ttu-id="7b135-107">Members</span><span class="sxs-lookup"><span data-stu-id="7b135-107">Members</span></span>

 <span data-ttu-id="7b135-108">_guid_</span><span class="sxs-lookup"><span data-stu-id="7b135-108">_guid_</span></span>
  
- <span data-ttu-id="7b135-109">[输出]创建对象的服务器的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7b135-109">[out] The GUID of the server that created the object.</span></span>
    
 <span data-ttu-id="7b135-110">_globcnt_</span><span class="sxs-lookup"><span data-stu-id="7b135-110">_globcnt_</span></span>
  
- <span data-ttu-id="7b135-111">[输出]标识的 Outlook 存储中的对象的 6 个字节唯一编号。</span><span class="sxs-lookup"><span data-stu-id="7b135-111">[out] A 6-byte unique number that identifies the object within the Outlook store.</span></span>
    
 <span data-ttu-id="7b135-112">_wLevel_</span><span class="sxs-lookup"><span data-stu-id="7b135-112">_wLevel_</span></span>
  
- <span data-ttu-id="7b135-113">[输出]Exchange 喜欢公用文件夹的条目 ID 层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="7b135-113">[out] The hierarchy level of the entry ID for an Exchange Favorite Public folder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b135-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b135-114">See also</span></span>



[<span data-ttu-id="7b135-115">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="7b135-115">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="7b135-116">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="7b135-116">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="7b135-117">FEID</span><span class="sxs-lookup"><span data-stu-id="7b135-117">FEID</span></span>](feid.md)

