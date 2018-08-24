---
title: SOrRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SOrRestriction
api_type:
- COM
ms.assetid: 6fee29ce-9a34-4e0c-bb71-03120c3f1117
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 054625601b496a8ec8f7745aa4cbc4715eed81a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585057"
---
# <a name="sorrestriction"></a><span data-ttu-id="f49fc-103">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="f49fc-103">SOrRestriction</span></span>

  
  
<span data-ttu-id="f49fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f49fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f49fc-105">描述用来限制应用于逻辑**OR**运算**或**限制。</span><span class="sxs-lookup"><span data-stu-id="f49fc-105">Describes an **OR** restriction which is used to apply a logical **OR** operation to a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f49fc-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f49fc-106">Header file:</span></span>  <br/> |<span data-ttu-id="f49fc-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f49fc-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SOrRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SOrRestriction;

```

## <a name="members"></a><span data-ttu-id="f49fc-108">Members</span><span class="sxs-lookup"><span data-stu-id="f49fc-108">Members</span></span>

 <span data-ttu-id="f49fc-109">**cRes**</span><span class="sxs-lookup"><span data-stu-id="f49fc-109">**cRes**</span></span>
  
> <span data-ttu-id="f49fc-110">由**lpRes**成员指向计数的数组中的结构。</span><span class="sxs-lookup"><span data-stu-id="f49fc-110">Count of structures in the array pointed to by the **lpRes** member.</span></span> 
    
 <span data-ttu-id="f49fc-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="f49fc-111">**lpRes**</span></span>
  
> <span data-ttu-id="f49fc-112">指向描述要使用逻辑**或**运算联接的限制的[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f49fc-112">Pointer to the [SRestriction](srestriction.md) structure describing the restriction to be joined using the logical **OR** operation.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f49fc-113">注解</span><span class="sxs-lookup"><span data-stu-id="f49fc-113">Remarks</span></span>

<span data-ttu-id="f49fc-114">有关**SOrRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="f49fc-114">For more information about the **SOrRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f49fc-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f49fc-115">See also</span></span>



[<span data-ttu-id="f49fc-116">SRestriction</span><span class="sxs-lookup"><span data-stu-id="f49fc-116">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="f49fc-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f49fc-117">MAPI Structures</span></span>](mapi-structures.md)

