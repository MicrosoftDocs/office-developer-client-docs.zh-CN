---
title: SNotRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SNotRestriction
api_type:
- COM
ms.assetid: e86ca032-d973-4b79-976e-5240ab38a0da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 174da93e7682246565b12c4fc4ffa6d1a9de065c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575061"
---
# <a name="snotrestriction"></a><span data-ttu-id="8df1f-103">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="8df1f-103">SNotRestriction</span></span>

  
  
<span data-ttu-id="8df1f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8df1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8df1f-105">介绍**不**限制，用来将逻辑**NOT**操作应用于限制。</span><span class="sxs-lookup"><span data-stu-id="8df1f-105">Describes a **NOT** restriction, which is used to apply a logical **NOT** operation to a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8df1f-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="8df1f-106">Header file:</span></span>  <br/> |<span data-ttu-id="8df1f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8df1f-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SNotRestriction
{
  ULONG ulReserved;
  LPSRestriction lpRes;
} SNotRestriction;

```

## <a name="members"></a><span data-ttu-id="8df1f-108">Members</span><span class="sxs-lookup"><span data-stu-id="8df1f-108">Members</span></span>

 <span data-ttu-id="8df1f-109">**ulReserved**</span><span class="sxs-lookup"><span data-stu-id="8df1f-109">**ulReserved**</span></span>
  
> <span data-ttu-id="8df1f-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="8df1f-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="8df1f-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="8df1f-111">**lpRes**</span></span>
  
> <span data-ttu-id="8df1f-112">指向[SRestriction](srestriction.md)结构，描述要加入到逻辑**NOT**运算符的限制。</span><span class="sxs-lookup"><span data-stu-id="8df1f-112">Pointer to a [SRestriction](srestriction.md) structure describing the restriction to be joined to the logical **NOT** operator.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8df1f-113">注解</span><span class="sxs-lookup"><span data-stu-id="8df1f-113">Remarks</span></span>

<span data-ttu-id="8df1f-114">有关**SNotRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="8df1f-114">For more information about the **SNotRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8df1f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8df1f-115">See also</span></span>



[<span data-ttu-id="8df1f-116">SRestriction</span><span class="sxs-lookup"><span data-stu-id="8df1f-116">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="8df1f-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="8df1f-117">MAPI Structures</span></span>](mapi-structures.md)

