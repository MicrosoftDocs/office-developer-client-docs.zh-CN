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
ms.openlocfilehash: bd9bfe4d1411b84a7811235aa68728afaefe64ab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439217"
---
# <a name="flatmtsidlist"></a><span data-ttu-id="4be19-103">FLATMTSIDLIST</span><span class="sxs-lookup"><span data-stu-id="4be19-103">FLATMTSIDLIST</span></span>

  
  
<span data-ttu-id="4be19-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4be19-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4be19-105">包含[MTSID](mtsid.md)结构的数组, 其中每个结构都包含一个 X. 400 邮件传输系统 (MTS) 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="4be19-105">Contains an array of [MTSID](mtsid.md) structures, each of which contains an X.400 message transport system (MTS) entry identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4be19-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4be19-106">Header file:</span></span>  <br/> |<span data-ttu-id="4be19-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4be19-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4be19-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="4be19-108">Related macros:</span></span>  <br/> |<span data-ttu-id="4be19-109">[CbFLATMTSIDLIST](cbflatmtsidlist.md)、 [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)</span><span class="sxs-lookup"><span data-stu-id="4be19-109">[CbFLATMTSIDLIST](cbflatmtsidlist.md), [CbNewFLATMTSIDLIST](cbnewflatmtsidlist.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cMTSIDs;
  ULONG cbMTSIDs;
  BYTE abMTSIDs[MAPI_DIM];
} FLATMTSIDLIST, FAR *LPFLATMTSIDLIST;

```

## <a name="members"></a><span data-ttu-id="4be19-110">Members</span><span class="sxs-lookup"><span data-stu-id="4be19-110">Members</span></span>

 <span data-ttu-id="4be19-111">**cMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="4be19-111">**cMTSIDs**</span></span>
  
> <span data-ttu-id="4be19-112">由**abMTSIDs**成员描述的数组中的**MTSID**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="4be19-112">Count of **MTSID** structures in the array described by the **abMTSIDs** member.</span></span> 
    
 <span data-ttu-id="4be19-113">**cbMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="4be19-113">**cbMTSIDs**</span></span>
  
> <span data-ttu-id="4be19-114">由**abMTSIDs**描述的数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4be19-114">Count of bytes in the array described by **abMTSIDs**.</span></span>
    
 <span data-ttu-id="4be19-115">**abMTSIDs**</span><span class="sxs-lookup"><span data-stu-id="4be19-115">**abMTSIDs**</span></span>
  
> <span data-ttu-id="4be19-116">包含一个或多个**MTSID**结构的字节数组。</span><span class="sxs-lookup"><span data-stu-id="4be19-116">Byte array that contains one or more **MTSID** structures.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4be19-117">说明</span><span class="sxs-lookup"><span data-stu-id="4be19-117">Remarks</span></span>

<span data-ttu-id="4be19-118">X. 400 邮件传递中的**FLATMTSIDLIST**结构与 MAPI 邮件中的[FLATENTRYLIST](flatentrylist.md)结构使用相对应。</span><span class="sxs-lookup"><span data-stu-id="4be19-118">The **FLATMTSIDLIST** structure's use in X.400 messaging corresponds to the [FLATENTRYLIST](flatentrylist.md) structure's use in MAPI messaging.</span></span> <span data-ttu-id="4be19-119">MAPI 在邮件处理过程中使用**FLATMTSIDLIST**结构来维护 X. 400 属性。</span><span class="sxs-lookup"><span data-stu-id="4be19-119">MAPI uses **FLATMTSIDLIST** structures to maintain X.400 properties during message handling.</span></span> <span data-ttu-id="4be19-120">服务提供程序在处理传入和传出的 X 400 邮件时使用**FLATMTSIDLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="4be19-120">Service providers use **FLATMTSIDLIST** structures when handling incoming and outgoing X.400 messages.</span></span> 
  
<span data-ttu-id="4be19-121">在**abMTSIDs**数组中, 每个**MTSID**结构在自然对齐的边界处对齐。</span><span class="sxs-lookup"><span data-stu-id="4be19-121">In the **abMTSIDs** array, each **MTSID** structure is aligned on a naturally aligned boundary.</span></span> <span data-ttu-id="4be19-122">填充包含额外的字节以确保任意两个**MTSID**结构之间的自然对齐。</span><span class="sxs-lookup"><span data-stu-id="4be19-122">Extra bytes are included as padding to make sure natural alignment between any two **MTSID** structures.</span></span> <span data-ttu-id="4be19-123">数组中的第一个**MTSID**结构始终正确对齐, 因为**abMTSIDs**成员的偏移量为8。</span><span class="sxs-lookup"><span data-stu-id="4be19-123">The first **MTSID** structure in the array is always aligned correctly because the offset of the **abMTSIDs** member is 8.</span></span> <span data-ttu-id="4be19-124">若要计算下一个结构的偏移量, 请使用第一项的大小向上舍入到接下来的4个。</span><span class="sxs-lookup"><span data-stu-id="4be19-124">To compute the offset of the next structure, use the size of the first entry rounded up to the next multiple of 4.</span></span> <span data-ttu-id="4be19-125">使用[CbNewMTSID](cbnewmtsid.md)宏计算**MTSID**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="4be19-125">Use the [CbNewMTSID](cbnewmtsid.md) macro to compute the size of an **MTSID** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4be19-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4be19-126">See also</span></span>



[<span data-ttu-id="4be19-127">CbNewFLATMTSIDLIST</span><span class="sxs-lookup"><span data-stu-id="4be19-127">CbNewFLATMTSIDLIST</span></span>](cbnewflatmtsidlist.md)
  
[<span data-ttu-id="4be19-128">FLATENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="4be19-128">FLATENTRYLIST</span></span>](flatentrylist.md)
  
[<span data-ttu-id="4be19-129">MTSID</span><span class="sxs-lookup"><span data-stu-id="4be19-129">MTSID</span></span>](mtsid.md)


[<span data-ttu-id="4be19-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="4be19-130">MAPI Structures</span></span>](mapi-structures.md)

