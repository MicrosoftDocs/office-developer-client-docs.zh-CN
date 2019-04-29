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
ms.openlocfilehash: 9b4ca4628f356142eb5303c064e3916474810fda
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437929"
---
# <a name="sorrestriction"></a><span data-ttu-id="47101-103">SOrRestriction</span><span class="sxs-lookup"><span data-stu-id="47101-103">SOrRestriction</span></span>

  
  
<span data-ttu-id="47101-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47101-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47101-105">描述用于对限制应用逻辑**OR**操作的**或**限制。</span><span class="sxs-lookup"><span data-stu-id="47101-105">Describes an **OR** restriction which is used to apply a logical **OR** operation to a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47101-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="47101-106">Header file:</span></span>  <br/> |<span data-ttu-id="47101-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="47101-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SOrRestriction
{
  ULONG cRes;
  LPSRestriction lpRes;
} SOrRestriction;

```

## <a name="members"></a><span data-ttu-id="47101-108">Members</span><span class="sxs-lookup"><span data-stu-id="47101-108">Members</span></span>

 <span data-ttu-id="47101-109">**cRes**</span><span class="sxs-lookup"><span data-stu-id="47101-109">**cRes**</span></span>
  
> <span data-ttu-id="47101-110">由**lpRes**成员指向的数组中的结构计数。</span><span class="sxs-lookup"><span data-stu-id="47101-110">Count of structures in the array pointed to by the **lpRes** member.</span></span> 
    
 <span data-ttu-id="47101-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="47101-111">**lpRes**</span></span>
  
> <span data-ttu-id="47101-112">指向描述要使用逻辑**OR**操作联接的限制的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="47101-112">Pointer to the [SRestriction](srestriction.md) structure describing the restriction to be joined using the logical **OR** operation.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="47101-113">说明</span><span class="sxs-lookup"><span data-stu-id="47101-113">Remarks</span></span>

<span data-ttu-id="47101-114">有关**SOrRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="47101-114">For more information about the **SOrRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="47101-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47101-115">See also</span></span>



[<span data-ttu-id="47101-116">SRestriction</span><span class="sxs-lookup"><span data-stu-id="47101-116">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="47101-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="47101-117">MAPI Structures</span></span>](mapi-structures.md)

