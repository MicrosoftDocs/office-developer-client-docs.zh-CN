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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418937"
---
# <a name="sexistrestriction"></a><span data-ttu-id="99c2d-103">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="99c2d-103">SExistRestriction</span></span>

  
  
<span data-ttu-id="99c2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="99c2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="99c2d-105">描述一个存在限制，该限制用于测试特定属性是否存在为表中的列。</span><span class="sxs-lookup"><span data-stu-id="99c2d-105">Describes an exist restriction which is used to test whether a particular property exists as a column in the table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="99c2d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="99c2d-106">Header file:</span></span>  <br/> |<span data-ttu-id="99c2d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="99c2d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SExistRestriction
{
  ULONG ulReserved1;
  ULONG ulPropTag;
  ULONG ulReserved2;
} SExistRestriction;

```

## <a name="members"></a><span data-ttu-id="99c2d-108">Members</span><span class="sxs-lookup"><span data-stu-id="99c2d-108">Members</span></span>

 <span data-ttu-id="99c2d-109">**ulReserved1**</span><span class="sxs-lookup"><span data-stu-id="99c2d-109">**ulReserved1**</span></span>
  
> <span data-ttu-id="99c2d-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="99c2d-110">Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="99c2d-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="99c2d-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="99c2d-112">属性标记，用于标识每行中是否存在要测试的列。</span><span class="sxs-lookup"><span data-stu-id="99c2d-112">Property tag identifying the column to be tested for existence in each row.</span></span>
    
 <span data-ttu-id="99c2d-113">**ulReserved2**</span><span class="sxs-lookup"><span data-stu-id="99c2d-113">**ulReserved2**</span></span>
  
> <span data-ttu-id="99c2d-114">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="99c2d-114">Reserved; must be zero.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="99c2d-115">备注</span><span class="sxs-lookup"><span data-stu-id="99c2d-115">Remarks</span></span>

<span data-ttu-id="99c2d-116">存在限制用于保证对涉及属性的其他类型的限制（如属性和内容限制）产生有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="99c2d-116">The exist restriction is used to guarantee meaningful results for other types of restrictions that involve properties, such as property and content restrictions.</span></span> <span data-ttu-id="99c2d-117">当涉及属性的限制被传递到 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md) 并且该属性不存在时，限制的结果将不确定。</span><span class="sxs-lookup"><span data-stu-id="99c2d-117">When a restriction that involves a property is passed to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) and the property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="99c2d-118">通过创建将属性限制与存在限制联接的 **AND** 限制，可以保证调用方得到准确的结果。</span><span class="sxs-lookup"><span data-stu-id="99c2d-118">By creating an **AND** restriction that joins the property restriction with an exist restriction, a caller can be guaranteed accurate results.</span></span> 
  
<span data-ttu-id="99c2d-119">存在限制不能与类型为 PT_OBJECT 的子对象属性一PT_OBJECT。</span><span class="sxs-lookup"><span data-stu-id="99c2d-119">Exist restrictions cannot be used with sub-object properties that have type PT_OBJECT.</span></span> 
  
<span data-ttu-id="99c2d-120">有关 **SExistRestriction** 结构详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="99c2d-120">For more information about the **SExistRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="99c2d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99c2d-121">See also</span></span>



[<span data-ttu-id="99c2d-122">SRestriction</span><span class="sxs-lookup"><span data-stu-id="99c2d-122">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="99c2d-123">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="99c2d-123">MAPI Structures</span></span>](mapi-structures.md)

