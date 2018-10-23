---
title: 默认邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: efa178eb-feb2-443f-8f6b-2ea53a456bf2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f7bf720f9105f6a81b832233cc648bc1d9ac91d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576909"
---
# <a name="default-message-stores"></a>默认邮件存储

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
默认邮件存储是客户端应用程序可将其用于通用邮件任务的存储。 如果要将邮件存储提供程序用作默认邮件存储，则邮件存储提供程序的许多可选功能将变为必需功能。 它们是：
  
- 实现特殊文件夹：收件箱、发件箱和搜索结果文件夹。
    
- 提供已读和未读报表。
    
- 允许提交传入和待发邮件。
    
- 允许创建任意邮件类别的邮件。
    
- 支持命名和多值属性。
    
- 支持 [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) 方法，即使邮件存储提供程序与传输提供程序紧密耦合。 
    
- 支持相关的内容表。 有关详细信息，请参阅[内容表](contents-tables.md)。
    
- 当待发邮件队列中有邮件时，支持 MAPI 后台处理程序通知。
    
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

