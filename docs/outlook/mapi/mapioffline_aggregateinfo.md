---
title: MAPIOFFLINE_AGGREGATEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2e502d28-ae09-49d9-a35a-5d77acdcd6f4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 24e16aeb1bbee1c35cf8fbd5813fb3e83b762187
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776373"
---
# <a name="mapiofflineaggregateinfo"></a><span data-ttu-id="eec94-103">MAPIOFFLINE_AGGREGATEINFO</span><span class="sxs-lookup"><span data-stu-id="eec94-103">MAPIOFFLINE_AGGREGATEINFO</span></span>

  
  
<span data-ttu-id="eec94-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="eec94-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="eec94-105">结构用于[HrCreateOfflineObj](hrcreateofflineobj.md)。</span><span class="sxs-lookup"><span data-stu-id="eec94-105">The structure is used with [HrCreateOfflineObj](hrcreateofflineobj.md).</span></span> 
  
```cpp
typedef struct
{
  ULONG            ulSize;
  IUnknown*          pOuterObj;
  IUnknown*          pRefTrackRoot;
} MAPIOFFLINE_AGGREGATEINFO;
```

## <a name="members"></a><span data-ttu-id="eec94-106">Members</span><span class="sxs-lookup"><span data-stu-id="eec94-106">Members</span></span>

 <span data-ttu-id="eec94-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="eec94-107">**ulSize**</span></span>
  
> <span data-ttu-id="eec94-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="eec94-108">The size of the structure.</span></span>
    
 <span data-ttu-id="eec94-109">**pOuterObj**</span><span class="sxs-lookup"><span data-stu-id="eec94-109">**pOuterObj**</span></span>
  
> <span data-ttu-id="eec94-110">指向此对象正在聚合到 IUnknown 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="eec94-110">A pointer to the IUnknown object onto which this object is being aggregated.</span></span> <span data-ttu-id="eec94-111">这将允许任何 QueryInterface 的调用将传递到创建的对象。</span><span class="sxs-lookup"><span data-stu-id="eec94-111">This allows any QueryInterface calls to pass through to the created object.</span></span>
    
 <span data-ttu-id="eec94-112">**pRefTrackRoot**</span><span class="sxs-lookup"><span data-stu-id="eec94-112">**pRefTrackRoot**</span></span>
  
> <span data-ttu-id="eec94-113">必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="eec94-113">Must be NULL.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eec94-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eec94-114">See also</span></span>



[<span data-ttu-id="eec94-115">HrCreateOfflineObj</span><span class="sxs-lookup"><span data-stu-id="eec94-115">HrCreateOfflineObj</span></span>](hrcreateofflineobj.md)
  
[<span data-ttu-id="eec94-116">MAPIOFFLINE_CREATEINFO</span><span class="sxs-lookup"><span data-stu-id="eec94-116">MAPIOFFLINE_CREATEINFO</span></span>](mapioffline_createinfo.md)

