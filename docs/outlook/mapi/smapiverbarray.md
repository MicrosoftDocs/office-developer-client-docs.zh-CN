---
title: SMAPIVerbArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIVerbArray
api_type:
- COM
ms.assetid: 8736f75c-3e95-42dd-9bc1-2f0bd23c4a02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7cba5dce60ce15ddb12776d619143849298aac9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433911"
---
# <a name="smapiverbarray"></a><span data-ttu-id="081f3-103">SMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="081f3-103">SMAPIVerbArray</span></span>

  
  
<span data-ttu-id="081f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="081f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="081f3-105">包含描述 MAPI 谓词的[SMAPIVerb](smapiverb.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="081f3-105">Contains an array of [SMAPIVerb](smapiverb.md) structures that describe MAPI verbs.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="081f3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="081f3-106">Header file:</span></span>  <br/> |<span data-ttu-id="081f3-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="081f3-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="081f3-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="081f3-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="081f3-109">CbMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="081f3-109">CbMAPIVerbArray</span></span>](cbmapiverbarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMAPIVerb;
  SMAPIVerb aMAPIVerb[MAPI_DIM];
} SMAPIVerbArray, FAR * LPMAPIVERBARRAY;

```

## <a name="members"></a><span data-ttu-id="081f3-110">Members</span><span class="sxs-lookup"><span data-stu-id="081f3-110">Members</span></span>

 <span data-ttu-id="081f3-111">**cForms**</span><span class="sxs-lookup"><span data-stu-id="081f3-111">**cForms**</span></span>
  
> <span data-ttu-id="081f3-112">数组中的谓词的计数。</span><span class="sxs-lookup"><span data-stu-id="081f3-112">Count of verbs in the array.</span></span>
    
 <span data-ttu-id="081f3-113">**aFormInfo**</span><span class="sxs-lookup"><span data-stu-id="081f3-113">**aFormInfo**</span></span>
  
> <span data-ttu-id="081f3-114">MAPI 谓词数组。</span><span class="sxs-lookup"><span data-stu-id="081f3-114">Array of MAPI verbs.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="081f3-115">说明</span><span class="sxs-lookup"><span data-stu-id="081f3-115">Remarks</span></span>

<span data-ttu-id="081f3-116">**SMAPIVerbArray**结构作为参数传递到[IMAPIFormInfo:: CalcVerbSet](imapiforminfo-calcverbset.md)方法中。</span><span class="sxs-lookup"><span data-stu-id="081f3-116">The **SMAPIVerbArray** structure is passed as a parameter in the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="081f3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="081f3-117">See also</span></span>



[<span data-ttu-id="081f3-118">SMAPIVerb</span><span class="sxs-lookup"><span data-stu-id="081f3-118">SMAPIVerb</span></span>](smapiverb.md)


[<span data-ttu-id="081f3-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="081f3-119">MAPI Structures</span></span>](mapi-structures.md)

