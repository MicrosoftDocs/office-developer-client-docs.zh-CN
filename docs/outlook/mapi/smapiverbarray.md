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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1767c86cb5390572b95530060f2295034ed35f43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778841"
---
# <a name="smapiverbarray"></a><span data-ttu-id="2bcee-103">SMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="2bcee-103">SMAPIVerbArray</span></span>

  
  
<span data-ttu-id="2bcee-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2bcee-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2bcee-105">包含描述 MAPI 谓词的[SMAPIVerb](smapiverb.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="2bcee-105">Contains an array of [SMAPIVerb](smapiverb.md) structures that describe MAPI verbs.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2bcee-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2bcee-106">Header file:</span></span>  <br/> |<span data-ttu-id="2bcee-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="2bcee-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="2bcee-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="2bcee-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="2bcee-109">CbMAPIVerbArray</span><span class="sxs-lookup"><span data-stu-id="2bcee-109">CbMAPIVerbArray</span></span>](cbmapiverbarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMAPIVerb;
  SMAPIVerb aMAPIVerb[MAPI_DIM];
} SMAPIVerbArray, FAR * LPMAPIVERBARRAY;

```

## <a name="members"></a><span data-ttu-id="2bcee-110">成员</span><span class="sxs-lookup"><span data-stu-id="2bcee-110">Members</span></span>

 <span data-ttu-id="2bcee-111">**cForms**</span><span class="sxs-lookup"><span data-stu-id="2bcee-111">**cForms**</span></span>
  
> <span data-ttu-id="2bcee-112">动词数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="2bcee-112">Count of verbs in the array.</span></span>
    
 <span data-ttu-id="2bcee-113">**aFormInfo**</span><span class="sxs-lookup"><span data-stu-id="2bcee-113">**aFormInfo**</span></span>
  
> <span data-ttu-id="2bcee-114">MAPI 谓词的数组。</span><span class="sxs-lookup"><span data-stu-id="2bcee-114">Array of MAPI verbs.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2bcee-115">备注</span><span class="sxs-lookup"><span data-stu-id="2bcee-115">Remarks</span></span>

<span data-ttu-id="2bcee-116">**SMAPIVerbArray**结构作为中[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法的参数传递。</span><span class="sxs-lookup"><span data-stu-id="2bcee-116">The **SMAPIVerbArray** structure is passed as a parameter in the [IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2bcee-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bcee-117">See also</span></span>



[<span data-ttu-id="2bcee-118">SMAPIVerb</span><span class="sxs-lookup"><span data-stu-id="2bcee-118">SMAPIVerb</span></span>](smapiverb.md)


[<span data-ttu-id="2bcee-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2bcee-119">MAPI Structures</span></span>](mapi-structures.md)

