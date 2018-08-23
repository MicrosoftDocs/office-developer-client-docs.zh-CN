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
ms.openlocfilehash: 84fb79b1922669db9c8e5d518a833a6866f11cea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589180"
---
# <a name="scommentrestriction"></a><span data-ttu-id="95772-103">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="95772-103">SCommentRestriction</span></span>

  
  
<span data-ttu-id="95772-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95772-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95772-105">描述注释限制，用来限制批注。</span><span class="sxs-lookup"><span data-stu-id="95772-105">Describes a comment restriction, which is used to annotate a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="95772-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="95772-106">Header file:</span></span>  <br/> |<span data-ttu-id="95772-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="95772-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCommentRestriction
{
  ULONG          cValues;
  LPSRestriction lpRes;
  LPSPropValue   lpProp;
} SCommentRestriction;

```

## <a name="members"></a><span data-ttu-id="95772-108">Members</span><span class="sxs-lookup"><span data-stu-id="95772-108">Members</span></span>

 <span data-ttu-id="95772-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="95772-109">**cValues**</span></span>
  
> <span data-ttu-id="95772-110">Count 属性值数组中的指向由**lpProp**成员。</span><span class="sxs-lookup"><span data-stu-id="95772-110">Count of property values in the array pointed to by the **lpProp** member.</span></span> 
    
 <span data-ttu-id="95772-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="95772-111">**lpRes**</span></span>
  
> <span data-ttu-id="95772-112">指向[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="95772-112">Pointer to an [SRestriction](srestriction.md) structure.</span></span> 
    
 <span data-ttu-id="95772-113">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="95772-113">**lpProp**</span></span>
  
> <span data-ttu-id="95772-114">给[SPropValue](spropvalue.md)结构，每个包含属性标记和的命名属性值的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="95772-114">Pointer to an array of [SPropValue](spropvalue.md) structures, each containing the property tag and value for a named property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="95772-115">注解</span><span class="sxs-lookup"><span data-stu-id="95772-115">Remarks</span></span>

<span data-ttu-id="95772-116">**SCommentRestriction**结构将与一组命名属性一起对象相关联。</span><span class="sxs-lookup"><span data-stu-id="95772-116">The **SCommentRestriction** structure associates an object together with a set of named properties.</span></span> <span data-ttu-id="95772-117">注释限制是与其他限制不同，因为不会评估这些。</span><span class="sxs-lookup"><span data-stu-id="95772-117">Comment restrictions are unlike other restrictions because they are not evaluated.</span></span> <span data-ttu-id="95772-118">即，它们将被忽略[IMAPITable::Restrict](imapitable-restrict.md)方法。</span><span class="sxs-lookup"><span data-stu-id="95772-118">That is, they are ignored by the [IMAPITable::Restrict](imapitable-restrict.md) method.</span></span> <span data-ttu-id="95772-119">没有任何影响后**IMAPITable::Restrict**呼叫已由[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的行。</span><span class="sxs-lookup"><span data-stu-id="95772-119">There is no effect on the rows returned by the [IMAPITable::QueryRows](imapitable-queryrows.md) method after an **IMAPITable::Restrict** call has been made.</span></span> 
  
<span data-ttu-id="95772-120">**SCommentRestriction**结构可用于保存在磁盘上时保留了一条限制的特定于应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="95772-120">The **SCommentRestriction** structure can be used to keep application-specific information with a restriction when it is saved on disk.</span></span> <span data-ttu-id="95772-121">例如，保存在属性限制中使用的命名属性的名称的客户端可以这样做**SCommentRestriction**结构中。</span><span class="sxs-lookup"><span data-stu-id="95772-121">For example, a client saving the name of a named property used in a property restriction can do so in an **SCommentRestriction** structure.</span></span> <span data-ttu-id="95772-122">因为关联的[SPropertyRestriction](spropertyrestriction.md)结构保留仅属性标记，保存的属性名称不能在属性限制中。</span><span class="sxs-lookup"><span data-stu-id="95772-122">Saving a property name is not possible in a property restriction because the associated [SPropertyRestriction](spropertyrestriction.md) structure holds only the property tag.</span></span> 
  
<span data-ttu-id="95772-123">有关**SCommentRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="95772-123">For more information about the **SCommentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95772-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95772-124">See also</span></span>



[<span data-ttu-id="95772-125">SPropValue</span><span class="sxs-lookup"><span data-stu-id="95772-125">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="95772-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="95772-126">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="95772-127">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="95772-127">SPropertyRestriction</span></span>](spropertyrestriction.md)


[<span data-ttu-id="95772-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="95772-128">MAPI Structures</span></span>](mapi-structures.md)

