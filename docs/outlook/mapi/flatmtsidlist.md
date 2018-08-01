---
title: FLATMTSIDLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATMTSIDLIST
api_type:
- COM
ms.assetid: b66c2815-72bc-4535-b34c-899bb830f29e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea841ef4bc551581fb2d9ca90201b4615e67f134
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774944"
---
# <a name="flatmtsidlist"></a><span data-ttu-id="9201a-103">FLATMTSIDLIST</span><span class="sxs-lookup"><span data-stu-id="9201a-103">FLATMTSIDLIST</span></span>

  
  
<span data-ttu-id="9201a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9201a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9201a-105">包含[MTSID](mtsid.md)结构，其中每个包含 X.400 邮件传输系统 (MTS) 条目标识符数组。</span><span class="sxs-lookup"><span data-stu-id="9201a-105">Contains an array of [MTSID](mtsid.md) structures, each of which contains an X.400 message transport system (MTS) entry identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9201a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9201a-106">Header file:</span></span>  <br/> |<span data-ttu-id="9201a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9201a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="9201a-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="9201a-108">Related macros:</span></span>  <br/> |<span data-ttu-id="9201a-109">[CbFLATMTSIDLIST](cbflatmtsidlist.md) [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)</span><span class="sxs-lookup"><span data-stu-id="9201a-109">[CbFLATMTSIDLIST](cbflatmtsidlist.md), [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cMTSIDs;
  ULONG cbMTSIDs;
  BYTE abMTSIDs[MAPI_DIM];
} FLATMTSIDLIST, FAR *LPFLATMTSIDLIST;

```

## <a name="members"></a><span data-ttu-id="9201a-110">Members</span><span class="sxs-lookup"><span data-stu-id="9201a-110">Members</span></span>

 <span data-ttu-id="9201a-111">**cMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="9201a-111">**cMTSIDs**</span></span>
  
> <span data-ttu-id="9201a-112">**MTSID**结构由**abMTSIDs**成员描述该数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="9201a-112">Count of **MTSID** structures in the array described by the **abMTSIDs** member.</span></span> 
    
 <span data-ttu-id="9201a-113">**cbMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="9201a-113">**cbMTSIDs**</span></span>
  
> <span data-ttu-id="9201a-114">描述**abMTSIDs**数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9201a-114">Count of bytes in the array described by **abMTSIDs**.</span></span>
    
 <span data-ttu-id="9201a-115">**abMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="9201a-115">**abMTSIDs**</span></span>
  
> <span data-ttu-id="9201a-116">包含一个或多个**MTSID**结构的字节数组。</span><span class="sxs-lookup"><span data-stu-id="9201a-116">Byte array that contains one or more **MTSID** structures.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9201a-117">说明</span><span class="sxs-lookup"><span data-stu-id="9201a-117">Remarks</span></span>

<span data-ttu-id="9201a-118">X.400 消息中的**FLATMTSIDLIST**结构使用对应于 MAPI 消息中的[FLATENTRYLIST](flatentrylist.md)结构的使用。</span><span class="sxs-lookup"><span data-stu-id="9201a-118">The **FLATMTSIDLIST** structure's use in X.400 messaging corresponds to the [FLATENTRYLIST](flatentrylist.md) structure's use in MAPI messaging.</span></span> <span data-ttu-id="9201a-119">MAPI 使用**FLATMTSIDLIST**结构消息处理期间维护 X.400 属性。</span><span class="sxs-lookup"><span data-stu-id="9201a-119">MAPI uses **FLATMTSIDLIST** structures to maintain X.400 properties during message handling.</span></span> <span data-ttu-id="9201a-120">服务提供商使用**FLATMTSIDLIST**结构处理传入和传出 X.400 邮件时。</span><span class="sxs-lookup"><span data-stu-id="9201a-120">Service providers use **FLATMTSIDLIST** structures when handling incoming and outgoing X.400 messages.</span></span> 
  
<span data-ttu-id="9201a-121">在**abMTSIDs**数组中，每个**MTSID**结构自然地对齐边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="9201a-121">In the **abMTSIDs** array, each **MTSID** structure is aligned on a naturally aligned boundary.</span></span> <span data-ttu-id="9201a-122">额外字节都作为包含填充使任意两个**MTSID**结构之间的确保自然对齐。</span><span class="sxs-lookup"><span data-stu-id="9201a-122">Extra bytes are included as padding to make sure natural alignment between any two **MTSID** structures.</span></span> <span data-ttu-id="9201a-123">该数组中的第一个**MTSID**结构对齐始终正确，因为**abMTSIDs**成员的偏移量为 8。</span><span class="sxs-lookup"><span data-stu-id="9201a-123">The first **MTSID** structure in the array is always aligned correctly because the offset of the **abMTSIDs** member is 8.</span></span> <span data-ttu-id="9201a-124">若要计算的偏移量的下一个结构，使用向上舍入到 4 的下一步的倍数的第一个条目的大小。</span><span class="sxs-lookup"><span data-stu-id="9201a-124">To compute the offset of the next structure, use the size of the first entry rounded up to the next multiple of 4.</span></span> <span data-ttu-id="9201a-125">使用[CbNewMTSID](cbnewmtsid.md)宏来计算**MTSID**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="9201a-125">Use the [CbNewMTSID](cbnewmtsid.md) macro to compute the size of an **MTSID** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9201a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9201a-126">See also</span></span>



[<span data-ttu-id="9201a-127">CbNewFLATMTSIDLIST</span><span class="sxs-lookup"><span data-stu-id="9201a-127">CbNewFLATMTSIDLIST</span></span>](cbnewflatmtsidlist.md)
  
[<span data-ttu-id="9201a-128">FLATENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="9201a-128">FLATENTRYLIST</span></span>](flatentrylist.md)
  
[<span data-ttu-id="9201a-129">MTSID</span><span class="sxs-lookup"><span data-stu-id="9201a-129">MTSID</span></span>](mtsid.md)


[<span data-ttu-id="9201a-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="9201a-130">MAPI Structures</span></span>](mapi-structures.md)

