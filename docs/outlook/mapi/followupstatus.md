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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418328"
---
# <a name="followupstatus"></a><span data-ttu-id="01e62-103">FollowUpStatus</span><span class="sxs-lookup"><span data-stu-id="01e62-103">FollowUpStatus</span></span>

  
  
<span data-ttu-id="01e62-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="01e62-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="01e62-105">指定邮件的不同后续状态。</span><span class="sxs-lookup"><span data-stu-id="01e62-105">Specifies the different follow-up statuses for a message.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="01e62-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="01e62-106">Quick info</span></span>

```cpp
enum FollowUpStatus { 
    flwupNone = 0, 
    flwupComplete, 
    flwupMarked, 
    flwupMAX}; 

```

## <a name="members"></a><span data-ttu-id="01e62-107">成员</span><span class="sxs-lookup"><span data-stu-id="01e62-107">Members</span></span>

 <span data-ttu-id="01e62-108">_flwupNone_</span><span class="sxs-lookup"><span data-stu-id="01e62-108">_flwupNone_</span></span>
  
> <span data-ttu-id="01e62-109">未指定任何后续操作。</span><span class="sxs-lookup"><span data-stu-id="01e62-109">No follow-up has been specified.</span></span>
    
 <span data-ttu-id="01e62-110">_flwupComplete_</span><span class="sxs-lookup"><span data-stu-id="01e62-110">_flwupComplete_</span></span>
  
> <span data-ttu-id="01e62-111">邮件已完成。</span><span class="sxs-lookup"><span data-stu-id="01e62-111">The message is complete.</span></span>
    
 <span data-ttu-id="01e62-112">_flwupMarked_</span><span class="sxs-lookup"><span data-stu-id="01e62-112">_flwupMarked_</span></span>
  
> <span data-ttu-id="01e62-113">邮件标记为后续跟进。</span><span class="sxs-lookup"><span data-stu-id="01e62-113">The message is marked for follow-up.</span></span>
    
 <span data-ttu-id="01e62-114">_flwupMAX_</span><span class="sxs-lookup"><span data-stu-id="01e62-114">_flwupMAX_</span></span>
  
> <span data-ttu-id="01e62-115">支持跟进的不同状态数。</span><span class="sxs-lookup"><span data-stu-id="01e62-115">The number of different statuses supported for follow-up.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01e62-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01e62-116">See also</span></span>



[<span data-ttu-id="01e62-117">PidTagFlagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="01e62-117">PidTagFlagStatus Canonical Property</span></span>](pidtagflagstatus-canonical-property.md)

