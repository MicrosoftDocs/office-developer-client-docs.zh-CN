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
ms.openlocfilehash: e59c0ba7810741943883b9e86e84c6fe141f3050
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774953"
---
# <a name="followupstatus"></a><span data-ttu-id="23932-103">FollowUpStatus</span><span class="sxs-lookup"><span data-stu-id="23932-103">FollowUpStatus</span></span>

  
  
<span data-ttu-id="23932-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="23932-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="23932-105">指定不同的后续状态邮件。</span><span class="sxs-lookup"><span data-stu-id="23932-105">Specifies the different follow-up statuses for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="23932-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="23932-106">Quick info</span></span>

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a><span data-ttu-id="23932-107">Members</span><span class="sxs-lookup"><span data-stu-id="23932-107">Members</span></span>

 <span data-ttu-id="23932-108">_flwupNone_</span><span class="sxs-lookup"><span data-stu-id="23932-108">_flwupNone_</span></span>
  
> <span data-ttu-id="23932-109">已指定没有进行后续工作。</span><span class="sxs-lookup"><span data-stu-id="23932-109">No follow-up has been specified.</span></span>
    
 <span data-ttu-id="23932-110">_flwupComplete_</span><span class="sxs-lookup"><span data-stu-id="23932-110">_flwupComplete_</span></span>
  
> <span data-ttu-id="23932-111">邮件已完成。</span><span class="sxs-lookup"><span data-stu-id="23932-111">The message is complete.</span></span>
    
 <span data-ttu-id="23932-112">_flwupMarked_</span><span class="sxs-lookup"><span data-stu-id="23932-112">_flwupMarked_</span></span>
  
> <span data-ttu-id="23932-113">邮件标记为需要后续操作。</span><span class="sxs-lookup"><span data-stu-id="23932-113">The message is marked for follow-up.</span></span>
    
 <span data-ttu-id="23932-114">_flwupMAX_</span><span class="sxs-lookup"><span data-stu-id="23932-114">_flwupMAX_</span></span>
  
> <span data-ttu-id="23932-115">为需要后续操作支持的不同状态数。</span><span class="sxs-lookup"><span data-stu-id="23932-115">The number of different statuses supported for follow-up.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23932-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23932-116">See also</span></span>



[<span data-ttu-id="23932-117">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="23932-117">PidTagFlagStatus Canonical Property</span></span>](pidtagflagstatus-canonical-property.md)

