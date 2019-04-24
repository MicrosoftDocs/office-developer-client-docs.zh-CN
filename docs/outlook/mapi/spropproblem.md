---
title: SPropProblem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropProblem
api_type:
- COM
ms.assetid: 55943197-fd11-442d-bb4b-0bff565b846e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3a0872c94459fc7c24d13e35adf335ef8012182
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357846"
---
# <a name="spropproblem"></a><span data-ttu-id="760a4-103">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="760a4-103">SPropProblem</span></span>

  
  
<span data-ttu-id="760a4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="760a4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="760a4-105">描述与涉及属性的操作相关的错误。</span><span class="sxs-lookup"><span data-stu-id="760a4-105">Describes an error that relate to an operation involving a property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="760a4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="760a4-106">Header file:</span></span>  <br/> |<span data-ttu-id="760a4-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="760a4-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SPropProblem
{
  ULONG ulIndex;
  ULONG ulPropTag;
  SCODE scode;
} SPropProblem, FAR *LPSPropProblem;

```

## <a name="members"></a><span data-ttu-id="760a4-108">Members</span><span class="sxs-lookup"><span data-stu-id="760a4-108">Members</span></span>

 <span data-ttu-id="760a4-109">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="760a4-109">**ulIndex**</span></span>
  
> <span data-ttu-id="760a4-110">属性标记数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="760a4-110">An index in an array of property tags.</span></span>
    
 <span data-ttu-id="760a4-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="760a4-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="760a4-112">包含错误的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="760a4-112">Property tag for the property that has the error.</span></span>
    
 <span data-ttu-id="760a4-113">**scode**</span><span class="sxs-lookup"><span data-stu-id="760a4-113">**scode**</span></span>
  
> <span data-ttu-id="760a4-114">描述属性问题的错误值。</span><span class="sxs-lookup"><span data-stu-id="760a4-114">Error value describing the problem with the property.</span></span> <span data-ttu-id="760a4-115">此值可以是任何 MAPI [SCODE](scode.md)值。</span><span class="sxs-lookup"><span data-stu-id="760a4-115">This value can be any MAPI [SCODE](scode.md) value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="760a4-116">注解</span><span class="sxs-lookup"><span data-stu-id="760a4-116">Remarks</span></span>

<span data-ttu-id="760a4-117">从以下方法返回**SPropProblem**结构的数组:</span><span class="sxs-lookup"><span data-stu-id="760a4-117">An array of **SPropProblem** structures is returned from the following methods:</span></span> 
  
- [<span data-ttu-id="760a4-118">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="760a4-118">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
    
- [<span data-ttu-id="760a4-119">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="760a4-119">IMAPISupport::DoCopyProps</span></span>](imapisupport-docopyprops.md)
    
- [<span data-ttu-id="760a4-120">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="760a4-120">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md)
    
- [<span data-ttu-id="760a4-121">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="760a4-121">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
- [<span data-ttu-id="760a4-122">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="760a4-122">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
    
- [<span data-ttu-id="760a4-123">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="760a4-123">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
    
- [<span data-ttu-id="760a4-124">IPropData::HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="760a4-124">IPropData::HrAddObjProps</span></span>](ipropdata-hraddobjprops.md)
    
<span data-ttu-id="760a4-125">**SPropProblem**结构包含一个由尝试修改或删除 MAPI 属性的操作产生的**SCODE**错误值。</span><span class="sxs-lookup"><span data-stu-id="760a4-125">An **SPropProblem** structure contains an **SCODE** error value that results from an operation trying to modify or delete a MAPI property.</span></span> 
  
<span data-ttu-id="760a4-126">有关**SPropProblem**结构如何处理与属性相关的错误的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="760a4-126">For more information about how the **SPropProblem** structure works with errors related to properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="760a4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="760a4-127">See also</span></span>



[<span data-ttu-id="760a4-128">SCODE</span><span class="sxs-lookup"><span data-stu-id="760a4-128">SCODE</span></span>](scode.md)
  
[<span data-ttu-id="760a4-129">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="760a4-129">SPropProblemArray</span></span>](spropproblemarray.md)


[<span data-ttu-id="760a4-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="760a4-130">MAPI Structures</span></span>](mapi-structures.md)

