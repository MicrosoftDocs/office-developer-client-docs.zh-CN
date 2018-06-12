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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a07a7737e9b9354514a2d5ac2ec37a393a3cd4e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778835"
---
# <a name="snotrestriction"></a><span data-ttu-id="c0ff1-103">SNotRestriction</span><span class="sxs-lookup"><span data-stu-id="c0ff1-103">SNotRestriction</span></span>

  
  
<span data-ttu-id="c0ff1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c0ff1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c0ff1-105">介绍**不**限制，用来将逻辑**NOT**操作应用于限制。</span><span class="sxs-lookup"><span data-stu-id="c0ff1-105">Describes a **NOT** restriction, which is used to apply a logical **NOT** operation to a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c0ff1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c0ff1-106">Header file:</span></span>  <br/> |<span data-ttu-id="c0ff1-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c0ff1-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SNotRestriction
{
  ULONG ulReserved;
  LPSRestriction lpRes;
} SNotRestriction;

```

## <a name="members"></a><span data-ttu-id="c0ff1-108">成员</span><span class="sxs-lookup"><span data-stu-id="c0ff1-108">Members</span></span>

 <span data-ttu-id="c0ff1-109">**ulReserved**</span><span class="sxs-lookup"><span data-stu-id="c0ff1-109">**ulReserved**</span></span>
  
> <span data-ttu-id="c0ff1-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="c0ff1-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="c0ff1-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="c0ff1-111">**lpRes**</span></span>
  
> <span data-ttu-id="c0ff1-112">指向[SRestriction](srestriction.md)结构，描述要加入到逻辑**NOT**运算符的限制。</span><span class="sxs-lookup"><span data-stu-id="c0ff1-112">Pointer to a [SRestriction](srestriction.md) structure describing the restriction to be joined to the logical **NOT** operator.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c0ff1-113">备注</span><span class="sxs-lookup"><span data-stu-id="c0ff1-113">Remarks</span></span>

<span data-ttu-id="c0ff1-114">有关**SNotRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="c0ff1-114">For more information about the **SNotRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c0ff1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0ff1-115">See also</span></span>



[<span data-ttu-id="c0ff1-116">SRestriction</span><span class="sxs-lookup"><span data-stu-id="c0ff1-116">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="c0ff1-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c0ff1-117">MAPI Structures</span></span>](mapi-structures.md)

