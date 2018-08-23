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
ms.openlocfilehash: 218238bea277a2d57c77fcc9d71cd622f7da42fa
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571946"
---
# <a name="sexistrestriction"></a><span data-ttu-id="55b1e-103">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="55b1e-103">SExistRestriction</span></span>

  
  
<span data-ttu-id="55b1e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55b1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55b1e-105">介绍用于测试的特定属性作为表中的列存在是否存在限制。</span><span class="sxs-lookup"><span data-stu-id="55b1e-105">Describes an exist restriction which is used to test whether a particular property exists as a column in the table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="55b1e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="55b1e-106">Header file:</span></span>  <br/> |<span data-ttu-id="55b1e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="55b1e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SExistRestriction
{
  ULONG ulReserved1;
  ULONG ulPropTag;
  ULONG ulReserved2;
} SExistRestriction;

```

## <a name="members"></a><span data-ttu-id="55b1e-108">Members</span><span class="sxs-lookup"><span data-stu-id="55b1e-108">Members</span></span>

 <span data-ttu-id="55b1e-109">**ulReserved1**</span><span class="sxs-lookup"><span data-stu-id="55b1e-109">**ulReserved1**</span></span>
  
> <span data-ttu-id="55b1e-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="55b1e-110">Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="55b1e-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="55b1e-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="55b1e-112">标识要测试的各行中存在的列的属性标记。</span><span class="sxs-lookup"><span data-stu-id="55b1e-112">Property tag identifying the column to be tested for existence in each row.</span></span>
    
 <span data-ttu-id="55b1e-113">**ulReserved2**</span><span class="sxs-lookup"><span data-stu-id="55b1e-113">**ulReserved2**</span></span>
  
> <span data-ttu-id="55b1e-114">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="55b1e-114">Reserved; must be zero.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="55b1e-115">注解</span><span class="sxs-lookup"><span data-stu-id="55b1e-115">Remarks</span></span>

<span data-ttu-id="55b1e-116">存在限制用于保证涉及属性，如属性和内容的限制的限制其他类型的有意义的结果。</span><span class="sxs-lookup"><span data-stu-id="55b1e-116">The exist restriction is used to guarantee meaningful results for other types of restrictions that involve properties, such as property and content restrictions.</span></span> <span data-ttu-id="55b1e-117">时涉及属性限制传递给[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)属性不存在，将不明确的限制结果。</span><span class="sxs-lookup"><span data-stu-id="55b1e-117">When a restriction that involves a property is passed to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) and the property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="55b1e-118">通过创建加入带存在限制在属性限制**和**限制，呼叫者可以保证准确的结果。</span><span class="sxs-lookup"><span data-stu-id="55b1e-118">By creating an **AND** restriction that joins the property restriction with an exist restriction, a caller can be guaranteed accurate results.</span></span> 
  
<span data-ttu-id="55b1e-119">存在限制不能用于具有类型 PT_OBJECT 的子对象属性。</span><span class="sxs-lookup"><span data-stu-id="55b1e-119">Exist restrictions cannot be used with sub-object properties that have type PT_OBJECT.</span></span> 
  
<span data-ttu-id="55b1e-120">有关**SExistRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="55b1e-120">For more information about the **SExistRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="55b1e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55b1e-121">See also</span></span>



[<span data-ttu-id="55b1e-122">SRestriction</span><span class="sxs-lookup"><span data-stu-id="55b1e-122">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="55b1e-123">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="55b1e-123">MAPI Structures</span></span>](mapi-structures.md)

