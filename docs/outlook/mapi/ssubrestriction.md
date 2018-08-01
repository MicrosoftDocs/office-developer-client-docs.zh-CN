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
ms.openlocfilehash: 152f3032876d6473f1716afa46507196cd5ecc55
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778870"
---
# <a name="ssubrestriction"></a><span data-ttu-id="63af8-103">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="63af8-103">SSubRestriction</span></span>

  
  
<span data-ttu-id="63af8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="63af8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="63af8-105">介绍用于筛选邮件的附件或收件人表的行的子对象限制。</span><span class="sxs-lookup"><span data-stu-id="63af8-105">Describes a sub-object restriction which is used to filter the rows of a message's attachment or recipient table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="63af8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="63af8-106">Header file:</span></span>  <br/> |<span data-ttu-id="63af8-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="63af8-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSubRestriction
{
  ULONG ulSubObject;
  LPSRestriction lpRes;
} SSubRestriction;

```

## <a name="members"></a><span data-ttu-id="63af8-108">Members</span><span class="sxs-lookup"><span data-stu-id="63af8-108">Members</span></span>

 <span data-ttu-id="63af8-109">**ulSubObject**</span><span class="sxs-lookup"><span data-stu-id="63af8-109">**ulSubObject**</span></span>
  
> <span data-ttu-id="63af8-110">要用作限制的目标的子对象的类型。</span><span class="sxs-lookup"><span data-stu-id="63af8-110">Type of sub-object to serve as the target for the restriction.</span></span> <span data-ttu-id="63af8-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="63af8-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="63af8-112">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="63af8-112">PR_MESSAGE_RECIPIENTS</span></span> 
  
> <span data-ttu-id="63af8-113">限制应用于邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="63af8-113">Apply the restriction to a message's recipient table.</span></span> 
    
<span data-ttu-id="63af8-114">PR_MESSAGE_ATTACHMENTS</span><span class="sxs-lookup"><span data-stu-id="63af8-114">PR_MESSAGE_ATTACHMENTS</span></span> 
  
>  <span data-ttu-id="63af8-115">限制应用于邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="63af8-115">Apply the restriction to a message's attachment table.</span></span> 
    
 <span data-ttu-id="63af8-116">**lpRes**</span><span class="sxs-lookup"><span data-stu-id="63af8-116">**lpRes**</span></span>
  
> <span data-ttu-id="63af8-117">指向[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="63af8-117">Pointer to an [SRestriction](srestriction.md) structure.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="63af8-118">说明</span><span class="sxs-lookup"><span data-stu-id="63af8-118">Remarks</span></span>

<span data-ttu-id="63af8-119">所有表不支持子对象的限制。</span><span class="sxs-lookup"><span data-stu-id="63af8-119">Sub-object restrictions are not supported by all tables.</span></span> <span data-ttu-id="63af8-120">通常情况下，仅文件夹内容表，搜索结果文件夹支持它们。</span><span class="sxs-lookup"><span data-stu-id="63af8-120">Typically, only folder contents tables and search results folders support them.</span></span> <span data-ttu-id="63af8-121">例如，子对象限制用来查找具有特定类型的附件或收件人的消息。</span><span class="sxs-lookup"><span data-stu-id="63af8-121">For example, sub-object restrictions are used to find a message that has a particular type of attachment or recipient.</span></span> 
  
<span data-ttu-id="63af8-122">如果实现不支持子对象限制，则从其[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)方法返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="63af8-122">If an implementation does not support sub-object restrictions, it returns MAPI_E_TOO_COMPLEX from its [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) methods.</span></span> 
  
<span data-ttu-id="63af8-123">有关限制的工作方式的一般讨论，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="63af8-123">For a general discussion of how restrictions work, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="63af8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63af8-124">See also</span></span>



[<span data-ttu-id="63af8-125">SRestriction</span><span class="sxs-lookup"><span data-stu-id="63af8-125">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="63af8-126">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="63af8-126">MAPI Structures</span></span>](mapi-structures.md)

