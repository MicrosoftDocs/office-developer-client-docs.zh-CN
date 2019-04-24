---
title: FollowUpStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c3d0f6c4-4597-784f-8d44-6e5d905895b4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2280ae9271ca73af33f395bf9e41a9ee8fa62f96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327522"
---
# <a name="followupstatus"></a><span data-ttu-id="23980-103">FollowUpStatus</span><span class="sxs-lookup"><span data-stu-id="23980-103">FollowUpStatus</span></span>

  
  
<span data-ttu-id="23980-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23980-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23980-105">指定邮件的不同跟进状态。</span><span class="sxs-lookup"><span data-stu-id="23980-105">Specifies the different follow-up statuses for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="23980-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="23980-106">Quick info</span></span>

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a><span data-ttu-id="23980-107">成员</span><span class="sxs-lookup"><span data-stu-id="23980-107">Members</span></span>

 <span data-ttu-id="23980-108">_flwupNone_</span><span class="sxs-lookup"><span data-stu-id="23980-108">_flwupNone_</span></span>
  
> <span data-ttu-id="23980-109">未指定跟进。</span><span class="sxs-lookup"><span data-stu-id="23980-109">No follow-up has been specified.</span></span>
    
 <span data-ttu-id="23980-110">_flwupComplete_</span><span class="sxs-lookup"><span data-stu-id="23980-110">_flwupComplete_</span></span>
  
> <span data-ttu-id="23980-111">邮件已完成。</span><span class="sxs-lookup"><span data-stu-id="23980-111">The message is complete.</span></span>
    
 <span data-ttu-id="23980-112">_flwupMarked_</span><span class="sxs-lookup"><span data-stu-id="23980-112">_flwupMarked_</span></span>
  
> <span data-ttu-id="23980-113">将邮件标记为待跟踪状态。</span><span class="sxs-lookup"><span data-stu-id="23980-113">The message is marked for follow-up.</span></span>
    
 <span data-ttu-id="23980-114">_flwupMAX_</span><span class="sxs-lookup"><span data-stu-id="23980-114">_flwupMAX_</span></span>
  
> <span data-ttu-id="23980-115">支持的不同状态的跟踪次数。</span><span class="sxs-lookup"><span data-stu-id="23980-115">The number of different statuses supported for follow-up.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23980-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23980-116">See also</span></span>



[<span data-ttu-id="23980-117">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="23980-117">PidTagFlagStatus Canonical Property</span></span>](pidtagflagstatus-canonical-property.md)

