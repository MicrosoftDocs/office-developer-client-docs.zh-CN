---
title: SCommentRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCommentRestriction
api_type:
- COM
ms.assetid: 07631ae1-981e-4c8e-a30b-1213904fe079
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3f66f513cc16bc479dd24c53804d751a396141f4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351413"
---
# <a name="scommentrestriction"></a><span data-ttu-id="46cbd-103">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="46cbd-103">SCommentRestriction</span></span>

  
  
<span data-ttu-id="46cbd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46cbd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46cbd-105">描述用于对限制进行批注的注释限制。</span><span class="sxs-lookup"><span data-stu-id="46cbd-105">Describes a comment restriction, which is used to annotate a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="46cbd-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="46cbd-106">Header file:</span></span>  <br/> |<span data-ttu-id="46cbd-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="46cbd-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCommentRestriction
{
  ULONG          cValues;
  LPSRestriction lpRes;
  LPSPropValue   lpProp;
} SCommentRestriction;

```

## <a name="members"></a><span data-ttu-id="46cbd-108">Members</span><span class="sxs-lookup"><span data-stu-id="46cbd-108">Members</span></span>

 <span data-ttu-id="46cbd-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="46cbd-109">**cValues**</span></span>
  
> <span data-ttu-id="46cbd-110">由**lpProp**成员指向的数组中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="46cbd-110">Count of property values in the array pointed to by the **lpProp** member.</span></span> 
    
 <span data-ttu-id="46cbd-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="46cbd-111">**lpRes**</span></span>
  
> <span data-ttu-id="46cbd-112">指向[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="46cbd-112">Pointer to an [SRestriction](srestriction.md) structure.</span></span> 
    
 <span data-ttu-id="46cbd-113">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="46cbd-113">**lpProp**</span></span>
  
> <span data-ttu-id="46cbd-114">指向[SPropValue](spropvalue.md)结构的数组的指针, 其中每个都包含命名属性的属性标记和值。</span><span class="sxs-lookup"><span data-stu-id="46cbd-114">Pointer to an array of [SPropValue](spropvalue.md) structures, each containing the property tag and value for a named property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="46cbd-115">注解</span><span class="sxs-lookup"><span data-stu-id="46cbd-115">Remarks</span></span>

<span data-ttu-id="46cbd-116">**SCommentRestriction**结构将对象与一组命名属性相关联。</span><span class="sxs-lookup"><span data-stu-id="46cbd-116">The **SCommentRestriction** structure associates an object together with a set of named properties.</span></span> <span data-ttu-id="46cbd-117">注释限制与其他限制不同, 因为它们不会进行评估。</span><span class="sxs-lookup"><span data-stu-id="46cbd-117">Comment restrictions are unlike other restrictions because they are not evaluated.</span></span> <span data-ttu-id="46cbd-118">即, [IMAPITable:: Restrict](imapitable-restrict.md)方法将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="46cbd-118">That is, they are ignored by the [IMAPITable::Restrict](imapitable-restrict.md) method.</span></span> <span data-ttu-id="46cbd-119">对 imapitable:: [QueryRows](imapitable-queryrows.md)方法返回的行在**imapitable:: Restrict**调用之后不会有任何影响。</span><span class="sxs-lookup"><span data-stu-id="46cbd-119">There is no effect on the rows returned by the [IMAPITable::QueryRows](imapitable-queryrows.md) method after an **IMAPITable::Restrict** call has been made.</span></span> 
  
<span data-ttu-id="46cbd-120">**SCommentRestriction**结构可用于将特定于应用程序的信息保存在磁盘上时保持限制。</span><span class="sxs-lookup"><span data-stu-id="46cbd-120">The **SCommentRestriction** structure can be used to keep application-specific information with a restriction when it is saved on disk.</span></span> <span data-ttu-id="46cbd-121">例如, 在属性限制中保存所使用的命名属性的名称的客户端可以在**SCommentRestriction**结构中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="46cbd-121">For example, a client saving the name of a named property used in a property restriction can do so in an **SCommentRestriction** structure.</span></span> <span data-ttu-id="46cbd-122">不能在属性限制中保存属性名称, 因为关联的[SPropertyRestriction](spropertyrestriction.md)结构仅保存属性标记。</span><span class="sxs-lookup"><span data-stu-id="46cbd-122">Saving a property name is not possible in a property restriction because the associated [SPropertyRestriction](spropertyrestriction.md) structure holds only the property tag.</span></span> 
  
<span data-ttu-id="46cbd-123">有关**SCommentRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="46cbd-123">For more information about the **SCommentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="46cbd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46cbd-124">See also</span></span>



[<span data-ttu-id="46cbd-125">SPropValue</span><span class="sxs-lookup"><span data-stu-id="46cbd-125">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="46cbd-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="46cbd-126">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="46cbd-127">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="46cbd-127">SPropertyRestriction</span></span>](spropertyrestriction.md)


[<span data-ttu-id="46cbd-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="46cbd-128">MAPI Structures</span></span>](mapi-structures.md)

