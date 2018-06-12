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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 32aa91d43e4674c0de20a0dbb670dcb9e2c782cf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778849"
---
# <a name="spropproblem"></a><span data-ttu-id="66a78-103">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="66a78-103">SPropProblem</span></span>

  
  
<span data-ttu-id="66a78-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="66a78-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="66a78-105">介绍错误与涉及属性的操作。</span><span class="sxs-lookup"><span data-stu-id="66a78-105">Describes an error that relate to an operation involving a property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66a78-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="66a78-106">Header file:</span></span>  <br/> |<span data-ttu-id="66a78-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="66a78-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SPropProblem
{
  ULONG ulIndex;
  ULONG ulPropTag;
  SCODE scode;
} SPropProblem, FAR *LPSPropProblem;

```

## <a name="members"></a><span data-ttu-id="66a78-108">成员</span><span class="sxs-lookup"><span data-stu-id="66a78-108">Members</span></span>

 <span data-ttu-id="66a78-109">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="66a78-109">**ulIndex**</span></span>
  
> <span data-ttu-id="66a78-110">属性标记的数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="66a78-110">An index in an array of property tags.</span></span>
    
 <span data-ttu-id="66a78-111">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="66a78-111">**ulPropTag**</span></span>
  
> <span data-ttu-id="66a78-112">属性标记具有错误的属性。</span><span class="sxs-lookup"><span data-stu-id="66a78-112">Property tag for the property that has the error.</span></span>
    
 <span data-ttu-id="66a78-113">**scode**</span><span class="sxs-lookup"><span data-stu-id="66a78-113">**scode**</span></span>
  
> <span data-ttu-id="66a78-114">描述属性的问题的错误值。</span><span class="sxs-lookup"><span data-stu-id="66a78-114">Error value describing the problem with the property.</span></span> <span data-ttu-id="66a78-115">此值可以是任何 MAPI [SCODE](scode.md)值。</span><span class="sxs-lookup"><span data-stu-id="66a78-115">This value can be any MAPI [SCODE](scode.md) value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="66a78-116">备注</span><span class="sxs-lookup"><span data-stu-id="66a78-116">Remarks</span></span>

<span data-ttu-id="66a78-117">从以下方法，则返回**SPropProblem**结构的数组：</span><span class="sxs-lookup"><span data-stu-id="66a78-117">An array of **SPropProblem** structures is returned from the following methods:</span></span> 
  
- [<span data-ttu-id="66a78-118">IMAPISupport::DoCopyTo</span><span class="sxs-lookup"><span data-stu-id="66a78-118">IMAPISupport::DoCopyTo</span></span>](imapisupport-docopyto.md)
    
- [<span data-ttu-id="66a78-119">IMAPISupport::DoCopyProps</span><span class="sxs-lookup"><span data-stu-id="66a78-119">IMAPISupport::DoCopyProps</span></span>](imapisupport-docopyprops.md)
    
- [<span data-ttu-id="66a78-120">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="66a78-120">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md)
    
- [<span data-ttu-id="66a78-121">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="66a78-121">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
- [<span data-ttu-id="66a78-122">IMAPIProp::CopyProps</span><span class="sxs-lookup"><span data-stu-id="66a78-122">IMAPIProp::CopyProps</span></span>](imapiprop-copyprops.md)
    
- [<span data-ttu-id="66a78-123">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="66a78-123">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
    
- [<span data-ttu-id="66a78-124">IPropData::HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="66a78-124">IPropData::HrAddObjProps</span></span>](ipropdata-hraddobjprops.md)
    
<span data-ttu-id="66a78-125">**SPropProblem**结构包含尝试修改或删除的 MAPI 属性的操作的结果**SCODE**错误值。</span><span class="sxs-lookup"><span data-stu-id="66a78-125">An **SPropProblem** structure contains an **SCODE** error value that results from an operation trying to modify or delete a MAPI property.</span></span> 
  
<span data-ttu-id="66a78-126">有关如何与错误相关属性结合使用**SPropProblem**结构的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="66a78-126">For more information about how the **SPropProblem** structure works with errors related to properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="66a78-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66a78-127">See also</span></span>



[<span data-ttu-id="66a78-128">SCODE</span><span class="sxs-lookup"><span data-stu-id="66a78-128">SCODE</span></span>](scode.md)
  
[<span data-ttu-id="66a78-129">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="66a78-129">SPropProblemArray</span></span>](spropproblemarray.md)


[<span data-ttu-id="66a78-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="66a78-130">MAPI Structures</span></span>](mapi-structures.md)

