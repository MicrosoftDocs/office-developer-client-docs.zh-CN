---
title: MAPIOFFLINE_AGGREGATEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2e502d28-ae09-49d9-a35a-5d77acdcd6f4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4775de0707eb90549f07525e3aa54ec5842f6050
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438160"
---
# <a name="mapioffline_aggregateinfo"></a><span data-ttu-id="7cbe1-103">MAPIOFFLINE_AGGREGATEINFO</span><span class="sxs-lookup"><span data-stu-id="7cbe1-103">MAPIOFFLINE_AGGREGATEINFO</span></span>

  
  
<span data-ttu-id="7cbe1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7cbe1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7cbe1-105">该结构与 [HrCreateOfflineObj 一起使用](hrcreateofflineobj.md)。</span><span class="sxs-lookup"><span data-stu-id="7cbe1-105">The structure is used with [HrCreateOfflineObj](hrcreateofflineobj.md).</span></span> 
  
```cpp
typedef struct
{
  ULONG            ulSize;
  IUnknown*          pOuterObj;
  IUnknown*          pRefTrackRoot;
} MAPIOFFLINE_AGGREGATEINFO;
```

## <a name="members"></a><span data-ttu-id="7cbe1-106">Members</span><span class="sxs-lookup"><span data-stu-id="7cbe1-106">Members</span></span>

 <span data-ttu-id="7cbe1-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="7cbe1-107">**ulSize**</span></span>
  
> <span data-ttu-id="7cbe1-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="7cbe1-108">The size of the structure.</span></span>
    
 <span data-ttu-id="7cbe1-109">**pOuterObj**</span><span class="sxs-lookup"><span data-stu-id="7cbe1-109">**pOuterObj**</span></span>
  
> <span data-ttu-id="7cbe1-110">指向要聚合此对象的 IUnknown 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7cbe1-110">A pointer to the IUnknown object onto which this object is being aggregated.</span></span> <span data-ttu-id="7cbe1-111">这允许任何 QueryInterface 调用传递到已创建的对象。</span><span class="sxs-lookup"><span data-stu-id="7cbe1-111">This allows any QueryInterface calls to pass through to the created object.</span></span>
    
 <span data-ttu-id="7cbe1-112">**pRefTrackRoot**</span><span class="sxs-lookup"><span data-stu-id="7cbe1-112">**pRefTrackRoot**</span></span>
  
> <span data-ttu-id="7cbe1-113">必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7cbe1-113">Must be NULL.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7cbe1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cbe1-114">See also</span></span>



[<span data-ttu-id="7cbe1-115">HrCreateOfflineObj</span><span class="sxs-lookup"><span data-stu-id="7cbe1-115">HrCreateOfflineObj</span></span>](hrcreateofflineobj.md)
  
[<span data-ttu-id="7cbe1-116">MAPIOFFLINE_CREATEINFO</span><span class="sxs-lookup"><span data-stu-id="7cbe1-116">MAPIOFFLINE_CREATEINFO</span></span>](mapioffline_createinfo.md)

