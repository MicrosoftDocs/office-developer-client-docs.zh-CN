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
ms.openlocfilehash: 21aafebefcb7e10e6ba432f2eb3cc5dc04978c20
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318086"
---
# <a name="avoiding-certain-methods-at-startup"></a>避免在启动时使用某些方法

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要提高启动时的性能，请避免进行以下调用：
  
- [IMAPISession::EnumAdrTypes](imapisession-enumadrtypes.md)
    
- [IMAPISession::GetStatusTable](imapisession-getstatustable.md)
    
- [IMAPISession::Logoff](imapisession-logoff.md)
    
- [IMAPISession::QueryIdentity](imapisession-queryidentity.md)
    
- [IMAPIStatus::ValidateState](imapistatus-validatestate.md)
    
仅当在 MAPI 后台处理程序或 MAPI 子系统上调用 **IMAPIStatus::ValidateState** 时会影响性能。 这些方法减慢启动过程的原因是它们在 MAPI 后台处理程序完成其启动任务之前无法完成。 
  
还应避免在启动时搜索邮件存储。 完成启动过程后再调用 [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)。 
  

