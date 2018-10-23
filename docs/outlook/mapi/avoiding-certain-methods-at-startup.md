---
title: 避免在启动时使用某些方法
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7bb86fc8-d1ae-4937-9919-86c3a0f5651d
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 5d26583ad7ad3b4a200daf321a8994e302b75a79
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580633"
---
# <a name="avoiding-certain-methods-at-startup"></a><span data-ttu-id="abfb1-103">避免在启动时使用某些方法</span><span class="sxs-lookup"><span data-stu-id="abfb1-103">Avoiding Certain Methods at Startup</span></span>

 
  
<span data-ttu-id="abfb1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="abfb1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="abfb1-105">若要提高启动时的性能，请避免进行以下调用：</span><span class="sxs-lookup"><span data-stu-id="abfb1-105">To improve performance at startup time, avoid making the following calls:</span></span>
  
- [<span data-ttu-id="abfb1-106">IMAPISession::EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="abfb1-106">IMAPISession::EnumAdrTypes</span></span>](imapisession-enumadrtypes.md)
    
- [<span data-ttu-id="abfb1-107">IMAPISession::GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="abfb1-107">IMAPISession::GetStatusTable</span></span>](imapisession-getstatustable.md)
    
- [<span data-ttu-id="abfb1-108">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="abfb1-108">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
    
- [<span data-ttu-id="abfb1-109">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="abfb1-109">IMAPISession::QueryIdentity</span></span>](imapisession-queryidentity.md)
    
- [<span data-ttu-id="abfb1-110">IMAPIStatus::ValidateState</span><span class="sxs-lookup"><span data-stu-id="abfb1-110">IMAPIStatus::ValidateState</span></span>](imapistatus-validatestate.md)
    
<span data-ttu-id="abfb1-111">仅当在 MAPI 后台处理程序或 MAPI 子系统上调用 **IMAPIStatus::ValidateState** 时会影响性能。</span><span class="sxs-lookup"><span data-stu-id="abfb1-111">The call to **IMAPIStatus::ValidateState** affects performance only when made on either the MAPI spooler or the MAPI subsystem.</span></span> <span data-ttu-id="abfb1-112">这些方法减慢启动过程的原因是它们在 MAPI 后台处理程序完成其启动任务之前无法完成。</span><span class="sxs-lookup"><span data-stu-id="abfb1-112">The reason that these methods slow startup processing is because they cannot complete until the MAPI spooler has finished its startup tasks.</span></span> 
  
<span data-ttu-id="abfb1-113">还应避免在启动时搜索邮件存储。</span><span class="sxs-lookup"><span data-stu-id="abfb1-113">You should also avoid searching the message store at startup time.</span></span> <span data-ttu-id="abfb1-114">完成启动过程后再调用 [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)。</span><span class="sxs-lookup"><span data-stu-id="abfb1-114">Make your [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) call when startup processing has finished.</span></span> 
  

