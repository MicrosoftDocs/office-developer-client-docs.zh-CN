---
title: FollowUpStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c3d0f6c4-4597-784f-8d44-6e5d905895b4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6b57ed45e067ce2debd40e033d386ad2b5ae895a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568516"
---
# <a name="followupstatus"></a><span data-ttu-id="16b2c-103">FollowUpStatus</span><span class="sxs-lookup"><span data-stu-id="16b2c-103">FollowUpStatus</span></span>

  
  
<span data-ttu-id="16b2c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16b2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16b2c-105">指定不同的后续状态邮件。</span><span class="sxs-lookup"><span data-stu-id="16b2c-105">Specifies the different follow-up statuses for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="16b2c-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="16b2c-106">Quick info</span></span>

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a><span data-ttu-id="16b2c-107">Members</span><span class="sxs-lookup"><span data-stu-id="16b2c-107">Members</span></span>

 <span data-ttu-id="16b2c-108">_flwupNone_</span><span class="sxs-lookup"><span data-stu-id="16b2c-108">_flwupNone_</span></span>
  
> <span data-ttu-id="16b2c-109">已指定没有进行后续工作。</span><span class="sxs-lookup"><span data-stu-id="16b2c-109">No follow-up has been specified.</span></span>
    
 <span data-ttu-id="16b2c-110">_flwupComplete_</span><span class="sxs-lookup"><span data-stu-id="16b2c-110">_flwupComplete_</span></span>
  
> <span data-ttu-id="16b2c-111">邮件已完成。</span><span class="sxs-lookup"><span data-stu-id="16b2c-111">The message is complete.</span></span>
    
 <span data-ttu-id="16b2c-112">_flwupMarked_</span><span class="sxs-lookup"><span data-stu-id="16b2c-112">_flwupMarked_</span></span>
  
> <span data-ttu-id="16b2c-113">邮件标记为需要后续操作。</span><span class="sxs-lookup"><span data-stu-id="16b2c-113">The message is marked for follow-up.</span></span>
    
 <span data-ttu-id="16b2c-114">_flwupMAX_</span><span class="sxs-lookup"><span data-stu-id="16b2c-114">_flwupMAX_</span></span>
  
> <span data-ttu-id="16b2c-115">为需要后续操作支持的不同状态数。</span><span class="sxs-lookup"><span data-stu-id="16b2c-115">The number of different statuses supported for follow-up.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="16b2c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16b2c-116">See also</span></span>



[<span data-ttu-id="16b2c-117">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="16b2c-117">PidTagFlagStatus Canonical Property</span></span>](pidtagflagstatus-canonical-property.md)

