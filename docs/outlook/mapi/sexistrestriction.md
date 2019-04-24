---
title: SExistRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SExistRestriction
api_type:
- COM
ms.assetid: 48d5ab42-ee70-4f6e-9184-18d22b08ea1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6e3cdcf3579b26776d9e278bb339758d4f56d890
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339275"
---
# <a name="sexistrestriction"></a><span data-ttu-id="51ebb-103">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="51ebb-103">SExistRestriction</span></span>

  
  
<span data-ttu-id="51ebb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="51ebb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="51ebb-105">描述用于测试特定属性是否作为表中的列存在的一个存在的限制。</span><span class="sxs-lookup"><span data-stu-id="51ebb-105">Describes an exist restriction which is used to test whether a particular property exists as a column in the table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="51ebb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="51ebb-106">Header file:</span></span>  <br/> |<span data-ttu-id="51ebb-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="51ebb-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SExistRestriction
{
  ULONG ulReserved1;
  ULONG ulPropTag;
  ULONG ulReserved2;
} SExistRestriction;

```

## <a name="members"></a><span data-ttu-id="51ebb-108">Members</span><span class="sxs-lookup"><span data-stu-id="51ebb-108">Members</span></span>

 <span data-ttu-id="51ebb-109">**ulReserved1**</span><span class="sxs-lookup"><span data-stu-id="51ebb-109">**ulReserved1**</span></span>
  
> <span data-ttu-id="51ebb-110">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="51ebb-110">Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="51ebb-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="51ebb-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="51ebb-112">用于标识要测试每行中是否存在的列的属性标记。</span><span class="sxs-lookup"><span data-stu-id="51ebb-112">Property tag identifying the column to be tested for existence in each row.</span></span>
    
 <span data-ttu-id="51ebb-113">**ulReserved2**</span><span class="sxs-lookup"><span data-stu-id="51ebb-113">**ulReserved2**</span></span>
  
> <span data-ttu-id="51ebb-114">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="51ebb-114">Reserved; must be zero.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="51ebb-115">注解</span><span class="sxs-lookup"><span data-stu-id="51ebb-115">Remarks</span></span>

<span data-ttu-id="51ebb-116">存在的限制用于确保对涉及属性的其他类型的限制 (如属性和内容限制) 的有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="51ebb-116">The exist restriction is used to guarantee meaningful results for other types of restrictions that involve properties, such as property and content restrictions.</span></span> <span data-ttu-id="51ebb-117">如果将涉及某个属性的限制传递给[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md) , 并且该属性不存在, 则限制的结果将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="51ebb-117">When a restriction that involves a property is passed to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) and the property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="51ebb-118">通过创建**和**限制将属性限制与存在的限制联接在一起, 可以保证正确结果的调用者。</span><span class="sxs-lookup"><span data-stu-id="51ebb-118">By creating an **AND** restriction that joins the property restriction with an exist restriction, a caller can be guaranteed accurate results.</span></span> 
  
<span data-ttu-id="51ebb-119">存在的限制不能与具有类型 PT_OBJECT 的子对象属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="51ebb-119">Exist restrictions cannot be used with sub-object properties that have type PT_OBJECT.</span></span> 
  
<span data-ttu-id="51ebb-120">有关**SExistRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="51ebb-120">For more information about the **SExistRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="51ebb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51ebb-121">See also</span></span>



[<span data-ttu-id="51ebb-122">SRestriction</span><span class="sxs-lookup"><span data-stu-id="51ebb-122">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="51ebb-123">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="51ebb-123">MAPI Structures</span></span>](mapi-structures.md)

