---
title: SSubRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSubRestriction
api_type:
- COM
ms.assetid: 5f7012f7-060d-4f2d-bcff-2aa9f6980e71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de92a1328eb9a089a7914978ab20ab0bf5c430ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581956"
---
# <a name="ssubrestriction"></a><span data-ttu-id="a217d-103">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="a217d-103">SSubRestriction</span></span>

  
  
<span data-ttu-id="a217d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a217d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a217d-105">介绍用于筛选邮件的附件或收件人表的行的子对象限制。</span><span class="sxs-lookup"><span data-stu-id="a217d-105">Describes a sub-object restriction which is used to filter the rows of a message's attachment or recipient table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a217d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a217d-106">Header file:</span></span>  <br/> |<span data-ttu-id="a217d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a217d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSubRestriction
{
  ULONG ulSubObject;
  LPSRestriction lpRes;
} SSubRestriction;

```

## <a name="members"></a><span data-ttu-id="a217d-108">Members</span><span class="sxs-lookup"><span data-stu-id="a217d-108">Members</span></span>

 <span data-ttu-id="a217d-109">**ulSubObject**</span><span class="sxs-lookup"><span data-stu-id="a217d-109">**ulSubObject**</span></span>
  
> <span data-ttu-id="a217d-110">要用作限制的目标的子对象的类型。</span><span class="sxs-lookup"><span data-stu-id="a217d-110">Type of sub-object to serve as the target for the restriction.</span></span> <span data-ttu-id="a217d-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="a217d-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="a217d-112">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="a217d-112">PR_MESSAGE_RECIPIENTS</span></span> 
  
> <span data-ttu-id="a217d-113">限制应用于邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="a217d-113">Apply the restriction to a message's recipient table.</span></span> 
    
<span data-ttu-id="a217d-114">PR_MESSAGE_ATTACHMENTS</span><span class="sxs-lookup"><span data-stu-id="a217d-114">PR_MESSAGE_ATTACHMENTS</span></span> 
  
>  <span data-ttu-id="a217d-115">限制应用于邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="a217d-115">Apply the restriction to a message's attachment table.</span></span> 
    
 <span data-ttu-id="a217d-116">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="a217d-116">**lpRes**</span></span>
  
> <span data-ttu-id="a217d-117">指向[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a217d-117">Pointer to an [SRestriction](srestriction.md) structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a217d-118">注解</span><span class="sxs-lookup"><span data-stu-id="a217d-118">Remarks</span></span>

<span data-ttu-id="a217d-119">所有表不支持子对象的限制。</span><span class="sxs-lookup"><span data-stu-id="a217d-119">Sub-object restrictions are not supported by all tables.</span></span> <span data-ttu-id="a217d-120">通常情况下，仅文件夹内容表，搜索结果文件夹支持它们。</span><span class="sxs-lookup"><span data-stu-id="a217d-120">Typically, only folder contents tables and search results folders support them.</span></span> <span data-ttu-id="a217d-121">例如，子对象限制用来查找具有特定类型的附件或收件人的消息。</span><span class="sxs-lookup"><span data-stu-id="a217d-121">For example, sub-object restrictions are used to find a message that has a particular type of attachment or recipient.</span></span> 
  
<span data-ttu-id="a217d-122">如果实现不支持子对象限制，则从其[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)方法返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="a217d-122">If an implementation does not support sub-object restrictions, it returns MAPI_E_TOO_COMPLEX from its [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) methods.</span></span> 
  
<span data-ttu-id="a217d-123">有关限制的工作方式的一般讨论，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="a217d-123">For a general discussion of how restrictions work, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a217d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a217d-124">See also</span></span>



[<span data-ttu-id="a217d-125">SRestriction</span><span class="sxs-lookup"><span data-stu-id="a217d-125">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="a217d-126">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a217d-126">MAPI Structures</span></span>](mapi-structures.md)

