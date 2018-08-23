---
title: 默认邮件存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: efa178eb-feb2-443f-8f6b-2ea53a456bf2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3f7bf720f9105f6a81b832233cc648bc1d9ac91d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576909"
---
# <a name="default-message-stores"></a>默认邮件存储区

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
默认邮件存储区是一种客户端应用程序可用于通用消息任务。 有大量的消息存储提供程序用作默认的邮件存储的消息存储提供程序是否成为所需的可选功能。 他们如下所示：
  
- 实现的特殊文件夹： 收件箱、 发件箱和搜索结果文件夹。
    
- 提供读取和 nonread 报告。
    
- 允许传入和传出邮件提交。
    
- 允许与任意邮件类的消息的创建。
    
- 支持的名为和多值属性。
    
- 即使与传输提供程序紧密耦合的消息存储提供程序支持的[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法。 
    
- 支持表关联的内容。 有关详细信息，请参阅[内容表](contents-tables.md)。
    
- 传出的邮件队列中邮件时，支持 MAPI 后台处理程序的通知。
    
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储区提供程序](developing-a-mapi-message-store-provider.md)

