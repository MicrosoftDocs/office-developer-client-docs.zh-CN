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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1437130caecd57344fc171d234c5391ea92e1d4b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778681"
---
# <a name="sandrestriction"></a><span data-ttu-id="0146d-103">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="0146d-103">SAndRestriction</span></span>

  
  
<span data-ttu-id="0146d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0146d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0146d-105">描述**和**限制，用来加入一组使用的逻辑**和**操作的限制。</span><span class="sxs-lookup"><span data-stu-id="0146d-105">Describes an **AND** restriction, which is used to join a group of restrictions using a logical **AND** operation.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0146d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0146d-106">Header file:</span></span>  <br/> |<span data-ttu-id="0146d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0146d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SAndRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SAndRestriction;

```

## <a name="members"></a><span data-ttu-id="0146d-108">成员</span><span class="sxs-lookup"><span data-stu-id="0146d-108">Members</span></span>

 <span data-ttu-id="0146d-109">**cRes**</span><span class="sxs-lookup"><span data-stu-id="0146d-109">**cRes**</span></span>
  
> <span data-ttu-id="0146d-110">由**lpRes**成员指向搜索限制数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="0146d-110">Count of search restrictions in the array pointed to by the **lpRes** member.</span></span> 
    
 <span data-ttu-id="0146d-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="0146d-111">**lpRes**</span></span>
  
> <span data-ttu-id="0146d-112">指向将合并在一起的逻辑**和**操作的[SRestriction](srestriction.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="0146d-112">Pointer to an array of [SRestriction](srestriction.md) structures that will be combined with a logical **AND** operation.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0146d-113">备注</span><span class="sxs-lookup"><span data-stu-id="0146d-113">Remarks</span></span>

<span data-ttu-id="0146d-114">如果及其所有子限制的计算都结果为 TRUE，则**SAndRestriction**的结果为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="0146d-114">The result of the **SAndRestriction** is TRUE if all its child restrictions evaluate to TRUE.</span></span> <span data-ttu-id="0146d-115">如果任何子限制的计算结果为 FALSE，则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0146d-115">It is FALSE if any child restriction evaluates to FALSE.</span></span> 
  
<span data-ttu-id="0146d-116">有关的类型的限制，说明如何构建其和示例代码，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="0146d-116">For a description of types of restrictions, how to build them, and sample code, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0146d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0146d-117">See also</span></span>



[<span data-ttu-id="0146d-118">SRestriction</span><span class="sxs-lookup"><span data-stu-id="0146d-118">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="0146d-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0146d-119">MAPI Structures</span></span>](mapi-structures.md)

