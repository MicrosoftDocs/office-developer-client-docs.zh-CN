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
ms.openlocfilehash: 07a1a0a1953d136da534fbdc6339d326c877bebf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426651"
---
# <a name="snotrestriction"></a><span data-ttu-id="a1efb-103">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="a1efb-103">SNotRestriction</span></span>

  
  
<span data-ttu-id="a1efb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a1efb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a1efb-105">描述用于将逻辑**非**操作应用于限制的**非**限制。</span><span class="sxs-lookup"><span data-stu-id="a1efb-105">Describes a **NOT** restriction, which is used to apply a logical **NOT** operation to a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a1efb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a1efb-106">Header file:</span></span>  <br/> |<span data-ttu-id="a1efb-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a1efb-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SNotRestriction
{
  ULONG ulReserved;
  LPSRestriction lpRes;
} SNotRestriction;

```

## <a name="members"></a><span data-ttu-id="a1efb-108">Members</span><span class="sxs-lookup"><span data-stu-id="a1efb-108">Members</span></span>

 <span data-ttu-id="a1efb-109">**ulReserved**</span><span class="sxs-lookup"><span data-stu-id="a1efb-109">**ulReserved**</span></span>
  
> <span data-ttu-id="a1efb-110">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="a1efb-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="a1efb-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="a1efb-111">**lpRes**</span></span>
  
> <span data-ttu-id="a1efb-112">指向描述要联接到逻辑**NOT**运算符的限制的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a1efb-112">Pointer to a [SRestriction](srestriction.md) structure describing the restriction to be joined to the logical **NOT** operator.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a1efb-113">说明</span><span class="sxs-lookup"><span data-stu-id="a1efb-113">Remarks</span></span>

<span data-ttu-id="a1efb-114">有关**SNotRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="a1efb-114">For more information about the **SNotRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1efb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1efb-115">See also</span></span>



[<span data-ttu-id="a1efb-116">SRestriction</span><span class="sxs-lookup"><span data-stu-id="a1efb-116">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="a1efb-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a1efb-117">MAPI Structures</span></span>](mapi-structures.md)

