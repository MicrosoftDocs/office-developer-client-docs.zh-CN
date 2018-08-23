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
ms.openlocfilehash: 5d26583ad7ad3b4a200daf321a8994e302b75a79
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580633"
---
# <a name="avoiding-certain-methods-at-startup"></a>避免在启动时使用某些方法

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
若要提高在启动时的性能，避免进行以下调用：
  
- [IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md)
    
- [IMAPISession::GetStatusTable](imapisession-getstatustable.md)
    
- [IMAPISession::Logoff](imapisession-logoff.md)
    
- [IMAPISession::QueryIdentity](imapisession-queryidentity.md)
    
- [IMAPIStatus::ValidateState](imapistatus-validatestate.md)
    
**IMAPIStatus::ValidateState**调用影响仅当 MAPI 后台处理程序或 MAPI 子系统上所做的性能。 这些方法，会启动处理降低的原因是因为他们无法完成，直到 MAPI 后台处理程序已完成其启动任务。 
  
您还应避免在启动时搜索消息存储库。 在完成后启动处理进行[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)呼叫。 
  

