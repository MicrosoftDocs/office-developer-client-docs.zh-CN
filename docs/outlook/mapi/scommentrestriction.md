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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430607"
---
# <a name="scommentrestriction"></a><span data-ttu-id="724bd-103">SCommentRestriction</span><span class="sxs-lookup"><span data-stu-id="724bd-103">SCommentRestriction</span></span>

  
  
<span data-ttu-id="724bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="724bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="724bd-105">描述注释限制，用于注释限制。</span><span class="sxs-lookup"><span data-stu-id="724bd-105">Describes a comment restriction, which is used to annotate a restriction.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="724bd-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="724bd-106">Header file:</span></span>  <br/> |<span data-ttu-id="724bd-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="724bd-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCommentRestriction
{
  ULONG          cValues;
  LPSRestriction lpRes;
  LPSPropValue   lpProp;
} SCommentRestriction;

```

## <a name="members"></a><span data-ttu-id="724bd-108">Members</span><span class="sxs-lookup"><span data-stu-id="724bd-108">Members</span></span>

 <span data-ttu-id="724bd-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="724bd-109">**cValues**</span></span>
  
> <span data-ttu-id="724bd-110">**lpProp** 成员指向的数组中的属性值计数。</span><span class="sxs-lookup"><span data-stu-id="724bd-110">Count of property values in the array pointed to by the **lpProp** member.</span></span> 
    
 <span data-ttu-id="724bd-111">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="724bd-111">**lpRes**</span></span>
  
> <span data-ttu-id="724bd-112">指向 [SRestriction 结构的](srestriction.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="724bd-112">Pointer to an [SRestriction](srestriction.md) structure.</span></span> 
    
 <span data-ttu-id="724bd-113">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="724bd-113">**lpProp**</span></span>
  
> <span data-ttu-id="724bd-114">指向 [SPropValue 结构的](spropvalue.md) 数组的指针，每个结构包含命名属性的属性标记和值。</span><span class="sxs-lookup"><span data-stu-id="724bd-114">Pointer to an array of [SPropValue](spropvalue.md) structures, each containing the property tag and value for a named property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="724bd-115">备注</span><span class="sxs-lookup"><span data-stu-id="724bd-115">Remarks</span></span>

<span data-ttu-id="724bd-116">**SCommentRestriction** 结构将对象与一组命名属性关联。</span><span class="sxs-lookup"><span data-stu-id="724bd-116">The **SCommentRestriction** structure associates an object together with a set of named properties.</span></span> <span data-ttu-id="724bd-117">注释限制与其他限制不同，因为它们未进行评估。</span><span class="sxs-lookup"><span data-stu-id="724bd-117">Comment restrictions are unlike other restrictions because they are not evaluated.</span></span> <span data-ttu-id="724bd-118">即 [，IMAPITable：：Restrict](imapitable-restrict.md) 方法将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="724bd-118">That is, they are ignored by the [IMAPITable::Restrict](imapitable-restrict.md) method.</span></span> <span data-ttu-id="724bd-119">执行 **IMAPITable：：Restrict** 调用后 [，对 IMAPITable：：QueryRows](imapitable-queryrows.md)方法返回的行没有影响。</span><span class="sxs-lookup"><span data-stu-id="724bd-119">There is no effect on the rows returned by the [IMAPITable::QueryRows](imapitable-queryrows.md) method after an **IMAPITable::Restrict** call has been made.</span></span> 
  
<span data-ttu-id="724bd-120">**SCommentRestriction** 结构可用于将特定于应用程序的信息保存在磁盘上时具有限制。</span><span class="sxs-lookup"><span data-stu-id="724bd-120">The **SCommentRestriction** structure can be used to keep application-specific information with a restriction when it is saved on disk.</span></span> <span data-ttu-id="724bd-121">例如，保存属性限制中使用的命名属性的名称的客户端可以在 **SCommentRestriction** 结构中这样做。</span><span class="sxs-lookup"><span data-stu-id="724bd-121">For example, a client saving the name of a named property used in a property restriction can do so in an **SCommentRestriction** structure.</span></span> <span data-ttu-id="724bd-122">在属性限制中无法保存属性名称，因为关联的 [SPropertyRestriction](spropertyrestriction.md) 结构仅保留属性标记。</span><span class="sxs-lookup"><span data-stu-id="724bd-122">Saving a property name is not possible in a property restriction because the associated [SPropertyRestriction](spropertyrestriction.md) structure holds only the property tag.</span></span> 
  
<span data-ttu-id="724bd-123">有关 **SCommentRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="724bd-123">For more information about the **SCommentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="724bd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="724bd-124">See also</span></span>



[<span data-ttu-id="724bd-125">SPropValue</span><span class="sxs-lookup"><span data-stu-id="724bd-125">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="724bd-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="724bd-126">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="724bd-127">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="724bd-127">SPropertyRestriction</span></span>](spropertyrestriction.md)


[<span data-ttu-id="724bd-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="724bd-128">MAPI Structures</span></span>](mapi-structures.md)

