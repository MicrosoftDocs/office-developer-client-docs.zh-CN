---
title: 避免在启动时使用某些方法
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7bb86fc8-d1ae-4937-9919-86c3a0f5651d
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: db327fdd239684140e4feeeb2a6045a2fcd5c410
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774610"
---
# <a name="avoiding-certain-methods-at-startup"></a><span data-ttu-id="a133a-103">避免在启动时使用某些方法</span><span class="sxs-lookup"><span data-stu-id="a133a-103">Avoiding Certain Methods at Startup</span></span>

 
  
<span data-ttu-id="a133a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a133a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a133a-105">若要提高在启动时的性能，避免进行以下调用：</span><span class="sxs-lookup"><span data-stu-id="a133a-105">To improve performance at startup time, avoid making the following calls:</span></span>
  
- [<span data-ttu-id="a133a-106">IMAPISession::EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="a133a-106">IMAPISession::EnumAdrTypes</span></span>](imapisession-enumadrtypes.md)
    
- [<span data-ttu-id="a133a-107">IMAPISession::GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="a133a-107">IMAPISession::GetStatusTable</span></span>](imapisession-getstatustable.md)
    
- [<span data-ttu-id="a133a-108">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="a133a-108">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
    
- [<span data-ttu-id="a133a-109">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="a133a-109">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)
    
- [<span data-ttu-id="a133a-110">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="a133a-110">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
    
<span data-ttu-id="a133a-111">**IMAPIStatus::ValidateState**调用影响仅当 MAPI 后台处理程序或 MAPI 子系统上所做的性能。</span><span class="sxs-lookup"><span data-stu-id="a133a-111">The call to **IMAPIStatus::ValidateState** affects performance only when made on either the MAPI spooler or the MAPI subsystem.</span></span> <span data-ttu-id="a133a-112">这些方法，会启动处理降低的原因是因为他们无法完成，直到 MAPI 后台处理程序已完成其启动任务。</span><span class="sxs-lookup"><span data-stu-id="a133a-112">The reason that these methods slow startup processing is because they cannot complete until the MAPI spooler has finished its startup tasks.</span></span> 
  
<span data-ttu-id="a133a-113">您还应避免在启动时搜索消息存储库。</span><span class="sxs-lookup"><span data-stu-id="a133a-113">You should also avoid searching the message store at startup time.</span></span> <span data-ttu-id="a133a-114">在完成后启动处理进行[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="a133a-114">Make your [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) call when startup processing has finished.</span></span> 
  

