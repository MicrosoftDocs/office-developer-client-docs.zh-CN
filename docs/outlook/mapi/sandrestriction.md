---
title: SAndRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SAndRestriction
api_type:
- COM
ms.assetid: 1b7dfe87-f87f-43e3-8332-a0d9c3f70d16
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da35c9c72f4cf3f076715a7a35a3e3514c672ceb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438881"
---
# <a name="sandrestriction"></a><span data-ttu-id="e9d55-103">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="e9d55-103">SAndRestriction</span></span>

  
  
<span data-ttu-id="e9d55-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9d55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9d55-105">描述了一个**和**限制, 该限制用于通过逻辑**AND**操作来联接一组限制。</span><span class="sxs-lookup"><span data-stu-id="e9d55-105">Describes an **AND** restriction, which is used to join a group of restrictions using a logical **AND** operation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e9d55-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e9d55-106">Header file:</span></span>  <br/> |<span data-ttu-id="e9d55-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e9d55-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SAndRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SAndRestriction;

```

## <a name="members"></a><span data-ttu-id="e9d55-108">Members</span><span class="sxs-lookup"><span data-stu-id="e9d55-108">Members</span></span>

 <span data-ttu-id="e9d55-109">**cRes**</span><span class="sxs-lookup"><span data-stu-id="e9d55-109">**cRes**</span></span>
  
> <span data-ttu-id="e9d55-110">由**lpRes**成员指向的数组中的搜索限制的计数。</span><span class="sxs-lookup"><span data-stu-id="e9d55-110">Count of search restrictions in the array pointed to by the **lpRes** member.</span></span> 
    
 <span data-ttu-id="e9d55-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="e9d55-111">**lpRes**</span></span>
  
> <span data-ttu-id="e9d55-112">指向将与逻辑**AND**运算组合在一起的[SRestriction](srestriction.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="e9d55-112">Pointer to an array of [SRestriction](srestriction.md) structures that will be combined with a logical **AND** operation.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e9d55-113">说明</span><span class="sxs-lookup"><span data-stu-id="e9d55-113">Remarks</span></span>

<span data-ttu-id="e9d55-114">如果其所有子限制的计算结果为 true, 则**SAndRestriction**的结果为 true。</span><span class="sxs-lookup"><span data-stu-id="e9d55-114">The result of the **SAndRestriction** is TRUE if all its child restrictions evaluate to TRUE.</span></span> <span data-ttu-id="e9d55-115">如果任何子限制的计算结果为 false, 则其值为 false。</span><span class="sxs-lookup"><span data-stu-id="e9d55-115">It is FALSE if any child restriction evaluates to FALSE.</span></span> 
  
<span data-ttu-id="e9d55-116">有关限制类型的说明、如何生成限制以及示例代码, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="e9d55-116">For a description of types of restrictions, how to build them, and sample code, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e9d55-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9d55-117">See also</span></span>



[<span data-ttu-id="e9d55-118">SRestriction</span><span class="sxs-lookup"><span data-stu-id="e9d55-118">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="e9d55-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e9d55-119">MAPI Structures</span></span>](mapi-structures.md)

